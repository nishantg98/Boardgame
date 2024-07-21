# BoardgameListingWebApp

## Description

**Board Game Database Full-Stack Web Application.**
This web application displays lists of board games and their reviews. While anyone can view the board game lists and reviews, they are required to log in to add/ edit the board games and their reviews. The 'users' have the authority to add board games to the list and add reviews, and the 'managers' have the authority to edit/ delete the reviews on top of the authorities of users.  

## Technologies

- Java
- Spring Boot
- Amazon Web Services(AWS) EC2
- Thymeleaf
- Thymeleaf Fragments
- HTML5
- CSS
- JavaScript
- Spring MVC
- JDBC
- H2 Database Engine (In-memory)
- JUnit test framework
- Spring Security
- Twitter Bootstrap
- Maven

## Features

- Full-Stack Application
- UI components created with Thymeleaf and styled with Twitter Bootstrap
- Authentication and authorization using Spring Security
  - Authentication by allowing the users to authenticate with a username and password
  - Authorization by granting different permissions based on the roles (non-members, users, and managers)
- Different roles (non-members, users, and managers) with varying levels of permissions
  - Non-members only can see the boardgame lists and reviews
  - Users can add board games and write reviews
  - Managers can edit and delete the reviews
- Deployed the application on AWS EC2
- JUnit test framework for unit testing
- Spring MVC best practices to segregate views, controllers, and database packages
- JDBC for database connectivity and interaction
- CRUD (Create, Read, Update, Delete) operations for managing data in the database
- Schema.sql file to customize the schema and input initial data
- Thymeleaf Fragments to reduce redundancy of repeating HTML elements (head, footer, navigation)

## How to Run

1. Clone the repository
2. Open the project in your IDE of choice
3. Run the application
4. To use initial user data, use the following credentials.
  - username: bugs    |     password: bunny (user role)
  - username: daffy   |     password: duck  (manager role)
5. You can also sign-up as a new user and customize your role to play with the application! 😊

## Project
**Project Highlights** 

![1721286749847](https://github.com/user-attachments/assets/5bc34f85-5e30-4013-894c-7b14adc4007a)




**Phase 1: Infrastructure Setup**

- Built a robust network environment for seamless communication.

- Set up an ELastic Kubernetes cluster for container orchestration in AWS.

- Implemented Jenkins for CI/CD automation.

- Integrated SonarQube for code quality analysis.

- Configured Nexus as the artifact repository.

- Deployed monitoring solutions for real-time insights.



**Phase 2:  Git Repository**

- Created a  Git repository.

- Ensured version control by pushing source code to the repository.



**Phase 3: Jenkins & CI/CD Pipeline Configuration**

- Installed necessary plugins in Jenkins for smooth pipeline execution.

- Designed a robust CI/CD pipeline with stages:

 - Tools definition

 - Compilation

 - Testing

 - File system scan/Dependency check scan

 - SonarQube analysis

 - Quality gate check

 - Building/packaging application

 - Publishing application artifacts to Nexus

 - Building & tagging Docker images

 - Vulnerability scanning of Docker images using Trivy

 - Pushing Docker images to Docker Hub repository

 - Deployment of application to EKS

 - Verification of deployment

 - Email notification upon completion



**Phase 4: Monitoring**

- System-level monitoring (CPU, RAM) using node_exporter.

- Website monitoring using blackbox_exporter.

- Utilized Prometheus & Grafana for effective visualization and analysis.

