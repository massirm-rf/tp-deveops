# Build The Project

To build this project, you will need to have the following installed:

* Docker & Docker Compose

To build the project, follow these steps:
s
1. Clone the repository.
2. Run the following command in the root directory of the project:
```bash
docker-compose up
```

The project will be built and the server will start by default on port 8060. To access the server, open http://localhost:8060 in your browser.


* Questions and Answers: 

1) Why should we run the container with a flag -e to give the environment variables ?

The -e flag is used to pass environment variables to the container, which are crucial for configuring the container at runtime. By using the -e flag, we ensure the container has the necessary settings for the application to run correctly.

2) When we talk about /docker-entrypoint-initdb.d it means inside the container, so you have to copy your directory's content and the container’s directory.

The /docker-entrypoint-initdb.d directory is used to set up the database when the container starts. Scripts in this directory run at startup to create and fill the database.

3) Why do we need a volume to be attached to our PostgreSQL container?

We attach a volume to the PostgreSQL container to save data. Without a volume, data is lost when the container stops. A volume keeps the data on the host machine, so it stays safe.

4) Why do we need a multistage build ?

A multistage build helps make the final image smaller. We build the app in one stage and then copy only the needed files to the final stage. This keeps the image size down.


5) Why do we need a reverse proxy ?

A reverse proxy directs requests to the right backend service. It can balance the load, route requests by path, and handle SSL. It also adds security features like rate limiting and authentication.

6) Why is Docker Compose so important ?

It is important because it lets us define and run multi-container apps easily. We list services, networks, and volumes in one file and manage the app with simple commands.

7) What is mvn clean verify supposed to do ?

`mvn clean verify` is a Maven command that cleans the project, compiles the code, runs tests, and packages the app. It's used to make sure the app is ready to deploy.

8) What are Testcontainers?

Testcontainers is a Java library that uses Docker containers for testing. It helps create and manage containers in tests, making it easy to test apps with databases and other services.

9 ) Secured Variables in GitHub, why ?

Securing variables in GitHub is important to keep sensitive info like API keys and passwords safe. If these get exposed, unauthorized users could access and harm the app.
