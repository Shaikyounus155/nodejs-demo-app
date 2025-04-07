# workflow
TASK 1: Automate Code Deployment Using CI/CD Pipeline (GitHub Actions)
•	Objective: Set up a CI/CD pipeline to build and deploy a web app.
In this project, we leverage Jenkins to create a robust CI/CD pipeline that integrates tools like Docker,  and OWASP Dependency Check to deliver secure and high-quality software.
Tools used:
1.	GitHub
2.	Jenkins
3.	Docker Hub
4.	Docker
5.	OWASP
6.	NodeJS

**GitHub**
     GitHub is a platform for hosting and sharing code using Git. It helps developers collaborate by tracking changes, managing versions, and reviewing code. You can create repositories (repos) to store and organize projects. It also offers features like issue tracking and CI/CD workflows.
     
**Jenkins**
Jenkins is an automation tool for building and deploying software. It uses pipelines to automate tasks like testing, building, and deploying code. It supports plugins to integrate with various tools. Jenkins makes Continuous Integration and Continuous Delivery (CI/CD) easy.

**Docker**
Docker is a tool to create, share, and run lightweight virtualized environments called containers. Containers package code and dependencies together for consistent behavior across systems. It simplifies app deployment and avoids “it works on my machine” issues. Docker images are reusable blueprints for containers.

**OWASP** (It’s  for additional security) 
it’s optional in this project
OWASP (Open Web Application Security Project) focuses on improving web application security. It provides resources like the OWASP Top 10, a list of the most critical security risks in web apps. Developers use it as a guide to build secure applications. OWASP also creates free tools for security testing.

**Node.js**
Node.js is a runtime that lets you run JavaScript outside the browser. It’s great for building fast and scalable server-side applications. Node.js uses non-blocking, event-driven programming for high performance. It’s commonly used for web servers, APIs, and real-time apps.

**Key Highlights**:
1.**Vulnerability Scanning**:
OWASP Dependency Check analyzes dependencies for vulnerabilities, ensuring no insecure libraries or frameworks are introduced.
 
2.**Dockerized Environments**:
          All stages of the pipeline run in Dockerized containers, ensuring consistency and simplifying environment management. 
          
3. **CI/CD Workflow:**
•	The pipeline automates build, test, and deploy processes, making it efficient and reliable.
•	Security and quality checks are seamlessly integrated into the pipeline, ensuring every release is both secure and robust.
 GitHub Repo:

**Lets implement it step-by-step,**
STEP-1:**Launch EC2 Instance with below Configurations**
1.	AMI : Amazon Linux Kernel 5.10
2.	Instance Type: T2.small
3.	EBS Volume : 5+ GB
4.	Security Groups : All Traffic
5.	
STEP-2:**Install Jenkins**
The source code to install Jenkins from official Documentation
 of Jenkins
 (https://www.jenkins.io/doc/)
#sudo wget -O /etc/yum.repos.d/jenkins.repo
 https://pkg.jenkins.io/redhat-stable/jenkins.repo

#sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

#yum install java-17-amazon-corretto -y 
#yum install jenkins -y
#systemctl start jenkins.service 
#systemctl enable jenkins.service 
#systemctl status jenkins.service

STEP-3:**Install Docker & GIT**
#yum install docker git -y
#systemctl start docker
#systemctl status docker
#chmod 777 ///var/run/docker.sock

STEP-4: **Install the following dependencies on Jenkins**
1.	NodeJS
2.	OWASP Dependency-Check
3.	Docker Pipeline

STEP-5: **Integrate all the tools to Jenkins**

STEP-6: **Add DockerHub Credentials**
Goto Jenkins Dashboard → Manage Jenkins → Credentials → System → Global credentials (unrestricted) → Add Username and password
username : dockerhub-username
password: dockerhub-password
credentials id : docker-password 

STEP-7: **Create a Jenkins Job**
Goto Jenkins Dashboard create a job as My-Deployment Name, select pipeline and click on it.
We write the pipeline then check the pipe line with run in the Jenkins it show that updates any errors in the pipeline through the plugin name Pipeline stage view in  Jenkins pipeline.
 
STEP-8: **Docker hub registry image**
Pull the docker image from dockerHub 
Image Name : Nodejs
To docker containers to lite weight the application and  balancing the traffic of containers.

STEP-9:  **Finally Deployed website with public IP and port number**.
http://<Jenkins-public-ip:8080\>










 



