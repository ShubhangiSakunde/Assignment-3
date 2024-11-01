# Secure DevOps Pipeline for Application Deployment

## Table of Contents
- [Project Description](#project-description)
- [Prerequisites](#prerequisites)
- [Tasks](#tasks)
  - [Task 1: Set Up Docker and Docker Compose](#task-1-set-up-docker-and-docker-compose)
  - [Task 2: Deploy Portainer for Docker Management](#task-2-deploy-portainer-for-docker-management)
  - [Task 3: Setup NextCloud Stack Using Docker Compose](#task-3-setup-nextcloud-stack-using-docker-compose)
  - [Task 4: Container Security Scanning with Clair](#task-4-container-security-scanning-with-clair)
  - [Task 5: Building and Deploying a Node.js Application with AWS CodePipeline](#task-5-building-and-deploying-a-nodejs-application-with-aws-codepipeline)
  - [Task 6: STRIDE Threat Modeling](#task-6-stride-threat-modeling)
- [Future Improvements](#future-improvements)
- [Credits](#credits)
- [References](#references)


---

## Project Description
This project guides the setup of a secure DevOps pipeline for a Python-based web application using AWS CodePipeline for CI/CD and Docker for containerization. Key goals include implementing security, monitoring, and maintaining secure access throughout the deployment pipeline with real-time monitoring and automated threat detection.

## Prerequisites
- A Linux server (Ubuntu 20.04 or higher) with Docker installed, at least 1GB RAM, 2 CPU cores, and 20GB free space.
- A personal GitHub account.

## Tasks

### Task 1: Set Up Docker and Docker Compose
1. Install Docker on an Ubuntu Server and verify the Docker version.
2. Install Docker Compose (latest stable version).
3. **Document Installation Steps**: Include each step in detail.
4. **Security Check for Docker Access**:
   - Limit Docker access to users with sudo privileges.
   - Verify and document the outcome by attempting access as a non-sudo user.

### Task 2: Deploy Portainer for Docker Management
1. Download and extract `portainer.zip` to your host.
2. Ensure the extracted folder structure includes `compose.yaml`.
3. **Deploy Portainer Stack**:
   - Start the Docker stack, document the steps, and show evidence of a running container.
   - Access the Portainer web interface and create an account.
4. **Log Monitoring**:
   - Display the three most recent lines of logs from the running stack.
   - Filter logs for suspicious activities, such as unauthorized access attempts.

### Task 3: Setup NextCloud Stack Using Docker Compose
1. Download and extract `nextcloud.zip`.
2. Explain the purpose of the `expose` key in `compose.yaml`.
3. **Setup NextCloud Stack**:
   - Configure the `compose.yaml` file.
   - Show the NextCloud web interface and document the URL.
4. **Command Line Interaction with Stack**:
   - Start, list services, tail logs, and document service start sequence.
   - Restart and manage services, ensuring the `db` service starts before `nc`.

### Task 4: Container Security Scanning with Clair
1. **Install Clair**:
   - Set up Clair on a server that is part of the Docker Swarm cluster.
   - Ensure Docker and PostgreSQL are installed, and initialize the PostgreSQL database for Clair.
2. **Run a Security Scan**:
   - Use `clairctl` to perform a security scan on the NextCloud container.
   - Document vulnerabilities by severity and list actions taken to address them.

### Task 5: Building and Deploying a Node.js Application with AWS CodePipeline
1. **Fork the GitHub Repository**:
   - Fork `Express-ES6-Sample` into your account.
   - Replace `package.json` with the provided version and push changes to your repository.
2. **Create a Four-Stage AWS CodePipeline**:
   - Source, Build, Test, and Deploy the Node.js application to AWS Elastic Beanstalk.
   - Document steps with screenshots and verify the successful deployment.
3. **Modify and Redeploy**:
   - Update the application code to display `My Student ID is xxxxxx. Welcome to Express`.
   - Push changes and verify the pipeline automatically detects, builds, and deploys them.

### Task 6: STRIDE Threat Modeling
1. **Create a Threat Model** using Microsoft Threat Modeling Tool:
   - Map system components: Database, Web Application, and User Interface.
2. **Identify Threats Using STRIDE**:
   - Document threats for each STRIDE category (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege).
3. **Mitigate Threats**:
   - Provide mitigation strategies for each threat.
   - Generate and review a report in the tool, then upload it to GitHub.

### Future Improvements
Potential enhancements to this project include:
- Adding automated vulnerability patching based on Clair scan results.
- Expanding the AWS CodePipeline stages to integrate automated compliance checks.
- Deploying additional security measures in the NextCloud stack, such as advanced data encryption.
  
### Credits
This project was developed as part of the ISEC6000 Secure DevOps course. Special thanks to the course instructors and the authors of referenced documentation for guidance.

### References
- [Docker Documentation](https://docs.docker.com/)
- [Portainer Documentation](https://docs.portainer.io/)
- [AWS CodePipeline Documentation](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html)
- [NextCloud](https://nextcloud.com/)
- University-provided course materials from the ISEC6000 Secure DevOps course.



