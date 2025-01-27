Students-Docker Project
This project is structured to manage a database, backend, and frontend using Docker containers. Follow the steps below to deploy the project.

Step 1: Database Setup
In this step, we configure and deploy the database using Docker.

Dockerfile: Students-Docker/DB/Dockerfile
SQL Initialization: Students-Docker/DB/init-db.sql
Instructions:
Navigate to the database directory:
cd Students-Docker/DB
Build the Docker image:
docker build -t students-db .
Run the database container:
docker run -d -p 3306:3306 --name students-db students-db
Step 2: Backend Setup
This step sets up the backend service that interacts with the database.

Dockerfile: Students-Docker/BE/Dockerfile
Ensure all necessary files are present in this directory.
Configure the database endpoint in the backend configuration file.
Instructions:
Navigate to the backend directory:
cd Students-Docker/BE
Build the Docker image:
docker build -t students-backend .
Run the backend container, making sure to link it to the database container:
docker run -d -p 8080:8080 --name students-backend --link students-db students-backend
Step 3: Frontend Setup
This step sets up the frontend that interacts with the backend service.

Dockerfile: Students-Docker/FE/Dockerfile
Ensure all necessary files are present in this directory.
Configure the backend endpoint in the index.html file.
Instructions:
Navigate to the frontend directory:
cd Students-Docker/FE
Build the Docker image:
docker build -t students-frontend .
Run the frontend container:
docker run -d -p 80:80 --name students-frontend students-frontend
Conclusion
By following these steps, you'll have a complete setup of the database, backend, and frontend services running in Docker containers. Make sure to configure the respective endpoints for the backend and frontend for full functionality.
