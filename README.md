# The Ultimate CI/CD Corporate DevOps Pipeline Project

## Description

**Board Game Database Full-Stack Web Application.**
This web application displays lists of board games and their reviews. While anyone can view the board game lists and reviews, they are required to log in to add/ edit the board games and their reviews. The 'users' have the authority to add board games to the list and add reviews, and the 'managers' have the authority to edit/ delete the reviews on top of the authorities of users.  

## Project
**Project Highlights** 
This project showcases a full-stack web application with a sign-up and login page, enabling users to create tasks post-registration. It covers the entire DevOps lifecycle, from infrastructure setup to continuous integration, delivery, and deployment on an EKS cluster. A journey that enriched learning experiences and conquered challenges, unveiling the true essence of DevOps. 

![1721286749847](https://github.com/user-attachments/assets/5bc34f85-5e30-4013-894c-7b14adc4007a)


**Phase 1: Infrastructure Setup**

- Built a robust network environment for seamless communication.

- Set up an ELastic Kubernetes cluster for container orchestration in AWS.

- Implemented Jenkins for CI/CD automation.

- Integrated SonarQube for code quality analysis.

- Configured Nexus as the artifact repository.

- Deployed monitoring solutions for real-time insights.

![Screenshot from 2024-07-21 01-39-37](https://github.com/user-attachments/assets/2583cd39-59d3-47e7-ab92-836b61010064)

![Screenshot from 2024-07-21 01-30-37](https://github.com/user-attachments/assets/ef854f57-479f-45ac-86cb-f0e5213f155b)

![Screenshot from 2024-07-21 01-30-52](https://github.com/user-attachments/assets/96aa35cd-e25a-4f1b-bb2b-574ef0d8f12b)



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

![Screenshot from 2024-07-21 01-33-30](https://github.com/user-attachments/assets/8eb9134c-a563-4f4b-b910-4535b7744a5a)

![Screenshot from 2024-07-21 01-32-25](https://github.com/user-attachments/assets/c6319a49-b84a-42dc-9d4c-177255c071a9)

![Screenshot from 2024-07-21 01-32-25](https://github.com/user-attachments/assets/007d2b90-c0e2-453e-8e0b-e38e11a5e187)

![Screenshot from 2024-07-21 01-29-46](https://github.com/user-attachments/assets/b7b8d130-9688-4260-9456-033595d608cc)




**Phase 4: Monitoring**

- System-level monitoring (CPU, RAM) using node_exporter.

- Website monitoring using blackbox_exporter.

- Utilized Prometheus & Grafana for effective visualization and analysis.

![Screenshot from 2024-07-21 01-29-38](https://github.com/user-attachments/assets/360728e2-b2fa-4360-8a1f-ab2d436b4de1)


![Screenshot from 2024-07-21 01-31-54](https://github.com/user-attachments/assets/25fc8543-9121-426d-bf38-357a01077ae2)


![Screenshot from 2024-07-21 21-19-33](https://github.com/user-attachments/assets/c8e8b7df-e54b-423d-b99e-93e1da60bfa4)







