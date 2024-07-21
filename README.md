# The Ultimate CI/CD Corporate DevOps Pipeline Project

## Description

**Board Game Database Full-Stack Web Application.**
This web application displays lists of board games and their reviews. While anyone can view the board game lists and reviews, they are required to log in to add/ edit the board games and their reviews. The 'users' have the authority to add board games to the list and add reviews, and the 'managers' have the authority to edit/ delete the reviews on top of the authorities of users.  

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

