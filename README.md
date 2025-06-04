# DevOps Assessment: Yii2 Application Deployment

## Overview

This project demonstrates the deployment of a Yii2 PHP application using Docker Swarm, NGINX, Ansible, and CI/CD with GitHub Actions.

## Prerequisites

- AWS EC2 instance with Ubuntu
- Domain pointing to EC2 instance
- Docker Hub account
- GitHub repository with secrets configured

## Setup Instructions

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/devops-assessment.git
   ```

2. **Configure Ansible Inventory:**

   Update `ansible/inventory.ini` with your EC2 instance details.

3. **Run Ansible Playbook:**

   ```bash
   cd ansible
   ansible-playbook -i inventory.ini playbook.yml
   ```

4. **Configure GitHub Secrets:**

   Add the following secrets to your GitHub repository:

   - `DOCKER_USERNAME`
   - `DOCKER_PASSWORD`
   - `EC2_HOST`
   - `EC2_SSH_KEY`

5. **Trigger Deployment:**

   Push changes to the `main` branch to trigger the GitHub Actions workflow.

## Testing Deployment

Access your application via the configured domain:

```bash
http://yourdomain.com
```

## Assumptions

- NGINX is installed on the host machine.
- Docker Swarm is initialized on the EC2 instance.
- The application is exposed on port 9000 and proxied by NGINX.

## Bonus Features

- **GitHub Secrets:** Used for storing sensitive information.
- **Health Checks:** Implemented in Docker Compose for the Yii2 application.
- **Monitoring:** Integration with Prometheus and Node Exporter can be added as needed.
