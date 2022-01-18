This is a spring boot application with two microservices that communicate with each other via Http. 

The application allows clients to register customers and then check whether the customer is fraudulent or not, If the customer is not fraudulent then the customer is saved in the database.

The customer microservice has a RESTful Api that allows you to post a customer with the following attributes; first name, last name and email.


To run the application, start both Customer microservice and Fraud microservices on their respective servers, postman can be used a REST client to post the customer.

The logins of the application's database can be found in the application.yml file of the project.

Docker Postgres Setup

Open up your terminal and make sure you're in the project directory:

docker compose up -d
Start container:

docker start postgres-demo
Stop container:

docker stop postgres-demo
Connection Info:

JDBC URL: `jdbc:postgresql://localhost:5050`

Password: `password`

Add new server
Host name: `postgres`

Username: `amigoscode`

Password: `password`

Note: This stores the data inside the container - when you delete the container, the data is deleted as well.

Connect to PSQL prompt from docker:
docker exec -it postgres-demo psql -U postgres

Configure Microservice to connect to Database:
View configuration in the application.yml in the project

Create database for customer and fraud in the main server in the pgAdmin page

Connection Info:
Username: `amigoscode`
 
JDBC URL: `jdbc:postgresql://localhost:5432/customer` for customer database 

JDBC URL: `jdbc:postgresql://localhost:5432/fraud` for fraud database

Password: `password`

