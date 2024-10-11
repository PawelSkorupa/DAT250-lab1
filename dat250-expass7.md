# DAT250-Lab7 Report

## Overview
Objective of assignment: obtain familiarity with Docker.

## Step 1: Setup and Using a Dockerized application: PostgreSQL
I pulled the Postgres docker image and then ran it using this command:

<code>docker run -p 5433:5432 -e POSTGRES_PASSWORD=**** -d --name my-postgres --rm postgres</code>

I used port 5432 of the container since it is the default port for Postgres. However, on my local machine I used port 5433 because I had a local instance of Postgres running.

I also needed to setup the POSTGRES_PASSWORD environmental variable in order for the container to work properly.

Then, I connected to the database using intelliJ built-in database tool and ran the script to create a user:

<code>CREATE USER jpa_client WITH PASSWORD 'secret';</code>

I updated the dependencies in gradle.build.kts and persistence.xml to fit the postgres database instead of H2.

I ran the test and it failed as expected. After that, I added the additional properties to persistence.xml to generate SQL scripts and ran the script from schema.up.sql file.
The test still failed, I needed to run additional query to the database in order to provide privilages to the postgres user:

<code>GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO jpa_client;</code>

After that, the test finished successfully.

## Step 2: Building you own dockerized application
I used the project from SPA exercise and in the repository, I added this dockerfile:

https://github.com/PawelSkorupa/DAT250-lab2-3-backend/blob/master/Dockerfile

I implemented a multi-stage build using gradle image for the build and temurin image for the runtime. I also created a new user so that the application is not ran by the root user.

After preparing the dockerfile, I ran my container and tested it in web browser - it worked exactly the same as if I ran the application directly on my machine.
