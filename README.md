# 🚀 CI/CD Pipeline for Java Web Application Deployment using Jenkins and Apache Tomcat

![Jenkins](https://img.shields.io/badge/Jenkins-CI/CD-red?logo=jenkins)
![Java](https://img.shields.io/badge/Java-17-orange?logo=openjdk)
![Maven](https://img.shields.io/badge/Maven-Build-blue?logo=apachemaven)
![Tomcat](https://img.shields.io/badge/Tomcat-Web_Server-yellow?logo=apachetomcat)
![Linux](https://img.shields.io/badge/Linux-Amazon_Linux-green?logo=linux)
![AWS](https://img.shields.io/badge/AWS-EC2-orange?logo=amazonaws)
![GitHub](https://img.shields.io/badge/GitHub-Repository-black?logo=github)

---

# 📌 Project Overview

This project demonstrates an **end-to-end Continuous Integration and Continuous Deployment (CI/CD) pipeline** using **Jenkins** to automate the build and deployment of a Java web application to a remote Apache Tomcat server hosted on AWS EC2.

The pipeline automatically performs the following tasks:

- Pulls source code from GitHub
- Builds the application using Maven
- Generates a WAR file
- Archives the build artifact
- Deploys the application to a remote Tomcat server using SSH
- Verifies deployment
- Cleans the Jenkins workspace

The entire deployment process is fully automated, eliminating manual deployment steps and reducing deployment time.

---

# 🎯 Project Objectives

The primary objectives of this project are:

- Learn Jenkins Declarative Pipelines
- Automate Java application builds
- Implement Continuous Integration
- Implement Continuous Deployment
- Practice secure SSH-based deployments
- Deploy applications to Apache Tomcat
- Gain hands-on DevOps experience using AWS EC2

---

# 🌍 Real World Use Case

In many organizations, developers manually build Java applications and copy WAR files to production servers.

This approach has several disadvantages:

- Human errors
- Time-consuming deployments
- Inconsistent deployments
- No deployment history
- Difficult rollback

Using Jenkins CI/CD solves these problems by automating the entire deployment lifecycle.

---

# 🏗 Project Architecture

```

                +----------------------+
                |      Developer       |
                +----------+-----------+
                           |
                    Git Push / Commit
                           |
                           ▼
                +----------------------+
                |    GitHub Repository |
                +----------+-----------+
                           |
                           ▼
                +----------------------+
                |      Jenkins CI      |
                +----------+-----------+
                           |
                 Checkout Source Code
                           |
                           ▼
                +----------------------+
                |     Maven Build      |
                +----------+-----------+
                           |
                 Generate WAR Artifact
                           |
                           ▼
                +----------------------+
                | Archive Artifact     |
                +----------+-----------+
                           |
                           ▼
                 Secure SSH Deployment
                           |
                           ▼
                +----------------------+
                | Apache Tomcat Server |
                +----------+-----------+
                           |
                           ▼
                +----------------------+
                | Java Web Application |
                +----------------------+

```

---

# ⚙ Infrastructure Used

| Component | Details |
|------------|----------|
| Cloud Provider | AWS |
| Compute Service | Amazon EC2 |
| Build Server | Jenkins |
| Application Server | Apache Tomcat |
| Build Tool | Maven |
| Programming Language | Java |
| Version Control | Git |
| Repository | GitHub |
| Deployment Method | SSH + SCP |
| Operating System | Amazon Linux |

---

# 🛠 Technologies Used

## DevOps Tools

- Jenkins
- Git
- GitHub
- Maven
- Apache Tomcat
- SSH
- Linux
- AWS EC2

---

## Programming Languages

- Java
- Groovy (Jenkins Pipeline)
- Shell Scripting

---

## AWS Services

- Amazon EC2
- Security Groups
- Key Pair

---

# 📂 Project Structure

```

Java-WebApp-CICD/
│
├── Jenkinsfile
├── pom.xml
├── README.md
├── src/
│ ├── main/
│ └── test/
│
├── target/
│ └── application.war
│
└── screenshots/
├── 01-jenkins-dashboard.png
├── 02-build-success.png
├── 03-console-output.png
├── 04-tomcat-server.png
├── 05-web-application.png
└── 06-pipeline-stage-view.png

```

---

# 🔧 Prerequisites

Before running this project, ensure the following components are installed and configured.

## Jenkins

- Installed
- Running
- Administrator Access

---

## Java

- JDK 17 (or compatible version)

Verify:

```bash
java -version
```

---

## Maven

Verify:

```bash
mvn -version
```

---

## Git

Verify:

```bash
git --version
```

---

## Apache Tomcat

Ensure:

- Installed
- Running
- Accessible on Port 8080

Verify:

```bash
http://<Tomcat-IP>:8080
```

---

## AWS EC2

This project uses two EC2 instances.

### Jenkins Server

Purpose:

- Build application
- Execute Jenkins Pipeline
- Deploy WAR

---

### Tomcat Server

Purpose:

- Host Java application
- Receive WAR file

---

# 🔐 AWS Security Groups

## Jenkins Server

Allow:

| Port | Purpose |
|-------|----------|
| 22 | SSH |
| 8080 | Jenkins |

---

## Tomcat Server

Allow:

| Port | Purpose |
|-------|----------|
| 22 | SSH Deployment |
| 8080 | Web Application |

---

# 🔑 SSH Configuration

Passwordless SSH authentication is configured between Jenkins and the Tomcat server.

Steps:

- Generate SSH Key
- Copy Public Key to Tomcat Server
- Store Private Key in Jenkins Credentials

Credential Type:

```
SSH Username with Private Key
```

Credential ID:

```
tomcat-ssh
```

---

# 📦 Maven Build Lifecycle

The pipeline uses Maven to build the Java application.

Lifecycle:

```

validate

↓

compile

↓

test

↓

package

↓

install

```

The generated WAR file is stored inside:

```

target/

```

---

# 🚀 CI/CD Workflow

```

Developer

↓

Git Push

↓

GitHub

↓

Jenkins Trigger

↓

Checkout

↓

Build

↓

Generate WAR

↓

Archive Artifact

↓

SSH Deployment

↓

Tomcat

↓

Application Live

```

---

# 📸 Screenshots

Add screenshots inside the **screenshots** folder.

Example:

```

screenshots/
│
├── Jenkins Dashboard
├── Pipeline Stage View
├── Successful Build
├── Console Output
├── GitHub Repository
├── Tomcat Manager
└── Running Application

```

---

# 📈 Features

✔ Continuous Integration

✔ Continuous Deployment

✔ Automated Build

✔ Maven Build Automation

✔ Secure SSH Deployment

✔ Artifact Archiving

✔ Deployment Verification

✔ Workspace Cleanup

✔ Jenkins Declarative Pipeline

✔ Remote Deployment on AWS EC2

---

# 🎯 Skills Demonstrated

- Jenkins
- CI/CD
- Git
- GitHub
- Maven
- Apache Tomcat
- Java
- Linux
- AWS EC2
- SSH
- Shell Scripting
- Pipeline Automation

---
# ⚙️ Jenkins Configuration

This project uses **Jenkins Declarative Pipeline** to automate the build and deployment process of a Java web application.

The Jenkins server is responsible for:

- Pulling source code from GitHub
- Compiling the application using Maven
- Creating the WAR file
- Archiving the build artifact
- Deploying the WAR file to a remote Apache Tomcat server
- Verifying successful deployment
- Cleaning up the workspace after execution

---

# 📦 Required Jenkins Plugins

Install the following plugins before running the pipeline.

| Plugin | Purpose |
|---------|---------|
| Git | Clone source code from GitHub |
| Pipeline | Execute Jenkinsfile |
| Pipeline Stage View | Visualize pipeline stages |
| SSH Agent | Authenticate with remote server |
| Credentials Binding | Secure credential management |
| Workspace Cleanup | Clean workspace after execution |
| Maven Integration | Maven build support |

---

# ☕ Configure JDK

Navigate to:

```
Manage Jenkins
    ↓
Global Tool Configuration
    ↓
JDK Installations
```

Example:

```
Name : JDK17

JAVA_HOME :
/usr/lib/jvm/java-17
```

---

# 📦 Configure Maven

Navigate to:

```
Manage Jenkins

↓

Global Tool Configuration

↓

Maven Installations
```

Example:

```
Name

MAVEN_HOME
```

This name should match the Jenkinsfile.

```groovy
tools {
    maven 'MAVEN_HOME'
}
```

---

# 🔐 Configure SSH Credentials

Navigate to:

```
Manage Jenkins

↓

Credentials

↓

Global

↓

Add Credentials
```

Select

```
Kind

SSH Username with Private Key
```

Fill in:

| Field | Value |
|---------|-------|
| Username | ec2-user |
| Private Key | Paste EC2 Private Key |
| ID | tomcat-ssh |

The Credential ID must match the Jenkinsfile.

```groovy
sshagent(credentials: ['tomcat-ssh'])
```

---

# 📁 Create Pipeline Job

Create a new Jenkins Pipeline Job.

```
Dashboard

↓

New Item

↓

Pipeline

↓

Create
```

Pipeline Settings

```
Definition

↓

Pipeline script from SCM
```

SCM

```
Git
```

Repository

```
https://github.com/yourusername/project.git
```

Branch

```
main
```

Script Path

```
Jenkinsfile
```

Save the configuration.

---

# 📜 Jenkinsfile Overview

The Jenkins pipeline consists of multiple stages that automate the entire deployment lifecycle.

Pipeline Flow

```
Checkout

↓

Verify Maven

↓

Build

↓

Archive Artifact

↓

Deploy

↓

Verify Deployment

↓

Post Actions
```

---

# 🔍 Stage 1 - Checkout

Purpose

- Clone the latest source code from GitHub.

Pipeline

```groovy
stage('Checkout') {
    steps {
        git branch: 'main',
            url: 'https://github.com/yourusername/project.git'
    }
}
```

Output

```
Checking out Revision...

Fetching upstream changes...

Repository cloned successfully.
```

---

# 🔍 Stage 2 - Verify Maven

Purpose

Verify Java and Maven installation before building the application.

Pipeline

```groovy
stage('Verify Maven') {
    steps {
        sh '''
        mvn --version
        java -version
        '''
    }
}
```

Expected Output

```
Apache Maven 3.9.x

Java version 17
```

Benefits

- Prevents build failures caused by missing tools.
- Confirms the correct Java version is being used.

---

# 🔍 Stage 3 - Build Application

Purpose

Compile the source code and package it into a WAR file.

Pipeline

```groovy
stage('Build') {
    steps {
        sh 'mvn clean package'
    }
}
```

Maven executes the following lifecycle:

```
Clean

↓

Compile

↓

Test

↓

Package
```

Generated Artifact

```
target/application.war
```

Benefits

- Automated build process
- Repeatable builds
- Consistent packaging

---

# 🔍 Stage 4 - Archive Artifact

Purpose

Store the generated WAR file inside Jenkins for future reference.

Pipeline

```groovy
stage('Archive Artifact') {
    steps {
        archiveArtifacts artifacts: 'target/*.war'
    }
}
```

Benefits

- Artifact version history
- Easy download
- Build traceability

---

# 🔍 Stage 5 - Deploy to Apache Tomcat

Purpose

Transfer the WAR file securely to the remote Tomcat server.

Pipeline

```groovy
stage('Deploy to Tomcat') {
    steps {
        sshagent(credentials: ['tomcat-ssh']) {
            sh """
            scp target/*.war \
            ${TOMCAT_USER}@${TOMCAT_HOST}:${DEPLOY_PATH}/
            """
        }
    }
}
```

Deployment Process

```
WAR File

↓

SSH Authentication

↓

Secure Copy (SCP)

↓

Tomcat Webapps Folder
```

Deployment Directory

```
/opt/tomcat/webapps
```

Benefits

- Secure deployment
- Remote deployment
- No manual copying required

---

# 🔍 Stage 6 - Verify Deployment

Purpose

Confirm that the WAR file has been successfully copied to the remote server.

Pipeline

```groovy
stage('Verify Deployment') {
    steps {
        sshagent(credentials: ['tomcat-ssh']) {
            sh """
            ssh ${TOMCAT_USER}@${TOMCAT_HOST} '
            ls -lh ${DEPLOY_PATH}
            '
            """
        }
    }
}
```

Example Output

```
application.war

ROOT/

Application Directory
```

Benefits

- Deployment confirmation
- Prevents silent deployment failures

---

# 🔍 Post Actions

After pipeline execution, Jenkins performs cleanup activities.

Success

```groovy
post {
    success {
        echo 'Application deployed successfully.'
    }
}
```

Failure

```groovy
post {
    failure {
        echo 'Pipeline failed.'
    }
}
```

Cleanup

```groovy
always {
    cleanWs()
}
```

Benefits

- Keeps Jenkins workspace clean
- Saves disk space
- Prevents stale artifacts

---

# 📦 Complete Deployment Workflow

```
Developer

↓

Git Push

↓

GitHub Repository

↓

Jenkins Pipeline

↓

Checkout Source Code

↓

Verify Java & Maven

↓

Compile Application

↓

Generate WAR

↓

Archive WAR

↓

SSH Authentication

↓

Secure Copy (SCP)

↓

Apache Tomcat Server

↓

Deploy WAR

↓

Verify Deployment

↓

Application Available
```

---

# 📊 Pipeline Benefits

- Fully Automated Deployment
- Repeatable Build Process
- Faster Delivery
- Reduced Human Errors
- Secure Deployment
- Versioned Build Artifacts
- Easy Troubleshooting
- Improved Reliability
- Production-like Workflow
- Infrastructure Ready for Scaling

---

# 🚀 Installation Guide

Follow the steps below to set up the project from scratch.

---

# Step 1 - Launch EC2 Instances

Create **two Amazon EC2 instances**.

| Server | Purpose |
|---------|----------|
| Jenkins Server | Build Server |
| Tomcat Server | Application Server |

Recommended Instance Type

```
t2.micro / t3.micro
```

Operating System

```
Amazon Linux 2023
```

---

# Step 2 - Install Java

Check Java

```bash
java -version
```

If Java is not installed:

```bash
sudo yum install java-17-amazon-corretto -y
```

Verify

```bash
java -version
```

---

# Step 3 - Install Maven

Check Maven

```bash
mvn -version
```

If not installed

```bash
sudo yum install maven -y
```

Verify

```bash
mvn -version
```

---

# Step 4 - Install Git

Check Git

```bash
git --version
```

Install

```bash
sudo yum install git -y
```

---

# Step 5 - Install Apache Tomcat

Download Tomcat

```bash
wget https://downloads.apache.org/tomcat/tomcat-10/v10.x.x/bin/apache-tomcat-10.x.x.tar.gz
```

Extract

```bash
tar -xvf apache-tomcat-10.x.x.tar.gz
```

Move

```bash
sudo mv apache-tomcat-10.x.x /opt/tomcat
```

Start Tomcat

```bash
/opt/tomcat/bin/startup.sh
```

Verify

```
http://<Tomcat-IP>:8080
```

---

# Step 6 - Configure Jenkins

Install Jenkins on the Jenkins server.

Install required plugins:

- Git
- Pipeline
- SSH Agent
- Maven Integration
- Workspace Cleanup
- Pipeline Stage View

Configure:

- JDK
- Maven
- SSH Credentials

---

# Step 7 - Configure Passwordless SSH

Generate SSH Key

```bash
ssh-keygen
```

Copy Public Key

```bash
ssh-copy-id ec2-user@<Tomcat-IP>
```

Test

```bash
ssh ec2-user@<Tomcat-IP>
```

If login works without asking for a password, SSH is configured successfully.

---

# Step 8 - Clone Repository

```bash
git clone https://github.com/yourusername/your-repository.git
```

---

# Step 9 - Create Jenkins Pipeline

Open Jenkins

```
Dashboard

↓

New Item

↓

Pipeline
```

Configure:

Repository

```
GitHub Repository URL
```

Branch

```
main
```

Pipeline Script

```
Jenkinsfile
```

Save.

---

# ▶ Running the Pipeline

Click

```
Build Now
```

Jenkins will automatically execute:

```
Checkout

↓

Verify Maven

↓

Compile

↓

Package

↓

Archive

↓

Deploy

↓

Verify

↓

Cleanup
```

---

# 🌐 Access the Application

After successful deployment

```
http://<Tomcat-IP>:8080/<ApplicationName>
```

Example

```
http://13.234.xxx.xxx:8080/OnlineBookStore
```

---

# 📋 Expected Pipeline Output

```
Started by user

Checking out repository...

Maven detected

Java detected

Compiling project...

Packaging WAR...

WAR generated successfully

Artifact archived

Connecting to remote server...

Copying WAR file...

Deployment completed

Verifying deployment...

Application deployed successfully

Cleaning workspace...
```

---

# 📂 Jenkins Workspace

During execution, Jenkins creates a temporary workspace.

Example

```
workspace/

↓

Source Code

↓

Build Files

↓

Target/

↓

application.war
```

After completion

```
Workspace Cleaned
```

---

# 📦 Artifact Storage

The generated WAR file is stored in Jenkins.

Navigate

```
Build

↓

Artifacts
```

Example

```
application.war
```

Artifacts can be downloaded anytime.

---

# 📸 Screenshots

Capture the following screenshots for documentation.

## Jenkins Dashboard

```
screenshots/
01-jenkins-dashboard.png
```

---

## Pipeline Stage View

```
screenshots/
02-stage-view.png
```

---

## Console Output

```
screenshots/
03-console-output.png
```

---

## Successful Build

```
screenshots/
04-build-success.png
```

---

## GitHub Repository

```
screenshots/
05-github-repository.png
```

---

## Apache Tomcat

```
screenshots/
06-tomcat-server.png
```

---

## Running Application

```
screenshots/
07-running-application.png
```

---

# 🔍 Troubleshooting

## Problem

```
Permission denied (publickey)
```

Reason

SSH authentication failed.

Solution

- Verify SSH credentials.
- Check Jenkins credential ID.
- Test SSH manually.

---

## Problem

```
scp: Permission denied
```

Reason

User cannot write to the Tomcat directory.

Solution

- Check directory permissions.
- Verify ownership.
- Use the correct deployment path.

---

## Problem

```
mvn: command not found
```

Reason

Maven is not installed or not configured.

Solution

- Install Maven.
- Configure Maven in Jenkins.
- Verify PATH.

---

## Problem

```
java: command not found
```

Reason

Java is missing.

Solution

Install JDK.

Verify

```bash
java -version
```

---

## Problem

```
Build Failed
```

Possible Reasons

- Compilation errors
- Missing dependencies
- Incorrect pom.xml
- Wrong Java version

Solution

Check

```
Console Output
```

---

## Problem

```
Connection timed out
```

Reason

Network issue.

Solution

- Verify EC2 Security Groups.
- Check SSH Port (22).
- Check firewall rules.

---

## Problem

```
Tomcat not reachable
```

Reason

Tomcat service is not running.

Solution

```bash
cd /opt/tomcat/bin

./startup.sh
```

---

## Problem

```
404 Not Found
```

Reason

Application was not deployed correctly.

Solution

- Check the WAR file.
- Verify the webapps directory.
- Restart Tomcat if necessary.

---

## Problem

```
Port 8080 not accessible
```

Reason

Security Group blocks traffic.

Solution

Allow

```
TCP 8080

Source

0.0.0.0/0
```

---

# 💡 Best Practices During Execution

- Use SSH keys instead of passwords.
- Keep credentials in Jenkins Credentials Store.
- Do not hardcode secrets in the Jenkinsfile.
- Verify Java and Maven versions before building.
- Archive artifacts for every successful build.
- Clean the workspace after every pipeline execution.
- Monitor Jenkins logs for failed builds.
- Test deployment on a staging server before production.
- Keep your Jenkinsfile under version control.
- Regularly update Jenkins plugins and dependencies.

---

# 🚀 Best Practices

This project follows several DevOps best practices to ensure a secure, maintainable, and production-ready CI/CD pipeline.

- Use Jenkins Declarative Pipelines (Pipeline as Code).
- Store pipeline definitions inside the Git repository.
- Keep credentials in Jenkins Credentials Store instead of hardcoding them.
- Use SSH keys for authentication instead of passwords.
- Archive build artifacts for traceability.
- Verify deployments after copying the artifact.
- Clean the Jenkins workspace after every build.
- Maintain separate Build and Application servers.
- Use version control for infrastructure and pipeline code.
- Monitor build history and console logs regularly.

---

# 🔒 Security Best Practices

- Never commit private keys to GitHub.
- Never hardcode usernames, passwords, or secrets.
- Restrict SSH access using Security Groups.
- Allow only required ports (22 and 8080).
- Rotate SSH keys periodically.
- Grant least-privilege permissions to deployment users.
- Keep Jenkins plugins up to date.
- Regularly patch the operating system.

---

# 📈 Future Enhancements

This project can be extended with additional DevOps tools and practices.

## Code Quality

- SonarQube Integration
- Checkstyle
- PMD

---

## Artifact Repository

- Nexus Repository
- JFrog Artifactory

---

## Containerization

- Dockerize the application
- Multi-stage Docker build
- Docker Compose

---

## Kubernetes

- Kubernetes Deployment
- Service
- Ingress
- ConfigMap
- Secret
- Persistent Volume

---

## Cloud

- AWS ECS
- AWS EKS
- Auto Scaling
- Application Load Balancer

---

## Infrastructure as Code

- Terraform
- AWS CloudFormation

---

## Configuration Management

- Ansible

---

## Monitoring

- Prometheus
- Grafana
- Node Exporter

---

## Notifications

- Email Notifications
- Slack Notifications
- Microsoft Teams Notifications

---

## Deployment Strategies

- Blue-Green Deployment
- Canary Deployment
- Rolling Updates

---

## GitOps

- Argo CD
- Flux CD

---

# 📚 Learning Outcomes

After completing this project, I gained practical experience in:

- Jenkins Declarative Pipelines
- Continuous Integration
- Continuous Deployment
- Maven Build Automation
- Git and GitHub Integration
- SSH-based Remote Deployment
- Apache Tomcat Administration
- Linux Server Management
- AWS EC2 Administration
- Artifact Management
- Pipeline Automation
- CI/CD Best Practices

---

# 💼 Resume Description

**Project:** CI/CD Pipeline for Java Web Application Deployment using Jenkins and Apache Tomcat

**Description**

Designed and implemented an end-to-end CI/CD pipeline using Jenkins to automate the build and deployment of a Java web application. Integrated GitHub for source control, Maven for build automation, SSH for secure deployment, and Apache Tomcat on AWS EC2 for application hosting. Automated artifact generation, deployment verification, and workspace cleanup to reduce manual effort and improve deployment reliability.

---

# 🎯 Skills Demonstrated

## DevOps

- Jenkins
- CI/CD
- Git
- GitHub
- Maven
- Linux
- Shell Scripting

## Cloud

- AWS EC2
- Security Groups
- SSH

## Web Technologies

- Java
- Apache Tomcat

## Automation

- Build Automation
- Deployment Automation
- Pipeline Automation

---

# ❓ Interview Questions

## Q1. Why did you use Jenkins?

**Answer**

Jenkins automates the software delivery process by integrating source code management, build automation, testing, artifact management, and deployment into a single pipeline.

---

## Q2. Why Maven?

**Answer**

Maven automates dependency management and project builds while providing a standardized project structure.

---

## Q3. Why deploy using SSH?

**Answer**

SSH provides secure communication between Jenkins and the remote application server, allowing automated deployments without exposing sensitive credentials.

---

## Q4. Why archive artifacts?

**Answer**

Artifact archiving stores generated WAR files for future reference, auditing, rollback, and download.

---

## Q5. Why verify deployment?

**Answer**

Verification confirms that the application has been successfully copied to the target server and helps detect deployment issues early.

---

## Q6. What happens if deployment fails?

**Answer**

The pipeline stops, marks the build as failed, displays error logs in the Jenkins console, and skips subsequent stages.

---

## Q7. What improvements would you make?

**Answer**

I would integrate SonarQube, Docker, Kubernetes, Nexus, Prometheus, Grafana, Slack notifications, and implement Blue-Green deployments for production environments.

---

# 📖 References

Official documentation used while building this project.

- Jenkins Documentation
- Apache Maven Documentation
- Apache Tomcat Documentation
- Git Documentation
- GitHub Documentation
- AWS EC2 Documentation
- OpenJDK Documentation

---

# 🤝 Contributing

Contributions are welcome.

If you would like to improve this project:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push the branch.
5. Open a Pull Request.

---

# 📄 License

This project is licensed under the MIT License.

Feel free to use and modify this project for learning purposes.

---

# 👨‍💻 Author

**Arava Deepak Sai Reddy**

DevOps | AWS | Linux | Docker | Kubernetes | Jenkins | Terraform | Python

GitHub:
[(deepaksaireddygit)](https://github.com/deepaksaireddygit)

LinkedIn:
[(Arava Deepak Sai Reddy)
](https://www.linkedin.com/in/arava-deepak-sai-reddy-367657319/?lipi=urn%3Ali%3Apage%3Ad_flagship3_feed%3BidjRmgALSIqOIB4Hb17GAQ%3D%3D)
---

# ⭐ If you found this project helpful

If this repository helped you learn CI/CD with Jenkins and Apache Tomcat, consider giving it a ⭐ on GitHub.

It motivates me to build and share more DevOps projects.

---

# 🎯 Project Summary

This project demonstrates a complete CI/CD workflow for deploying a Java web application using Jenkins and Apache Tomcat on AWS EC2. It covers source code management, automated builds, artifact creation, secure remote deployment, deployment verification, and cleanup. The implementation reflects industry-standard DevOps practices and provides a strong foundation for integrating advanced tools such as Docker, Kubernetes, Terraform, Ansible, SonarQube, Prometheus, and GitOps platforms.

---

## 📌 Repository Checklist

- ✅ Jenkins Declarative Pipeline
- ✅ GitHub Integration
- ✅ Maven Build
- ✅ WAR Artifact Generation
- ✅ Artifact Archiving
- ✅ Secure SSH Deployment
- ✅ Remote Apache Tomcat Deployment
- ✅ AWS EC2 Infrastructure
- ✅ Deployment Verification
- ✅ Workspace Cleanup
- ✅ Professional Documentation
- ✅ Resume Ready
- ✅ Interview Ready

![AWS EC2 instances](screenshots/instances.png)

![Jenkins pipeline stage view](screenshots/pipeine_jenkins.png)

![Archived Jenkins WAR artifact](screenshots/artifact.png)

![WAR deployed to Tomcat](screenshots/tomact_ec2.png)

![Online Bookstore running on Tomcat](screenshots/tomcat_webpage.png)
