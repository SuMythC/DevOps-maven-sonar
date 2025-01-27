# DevOps Jenkins Pipeline: Maven, SonarQube, Trivy, Docker, Kubernetes

![Project Overview](https://github.com/user-attachments/assets/f067cfce-6233-4cf2-bf76-ee0c3ae52d4a)

This repository demonstrates a Jenkins pipeline integrating Maven, SonarQube, Trivy, Docker, and Kubernetes for continuous integration and deployment.

## Jenkins Pipeline: Maven, SonarQube, and Trivy

The pipeline automates the process of building, scanning, and deploying applications. Here's how it's set up:

### Pipeline Configuration
The Jenkins pipeline script is stored in this repository. Below is a screenshot of the pipeline configuration within Jenkins.

![Jenkins Pipeline Configuration](https://github.com/user-attachments/assets/f523701c-e2e6-45cf-a12b-c529174df45a)

### Jenkins Script
The pipeline script includes stages for:

- Building with Maven
- Running security scans with Trivy
- Analyzing code with SonarQube

![Jenkins Pipeline Script](https://github.com/user-attachments/assets/3e2739f6-b46d-4491-8b89-b493519499bd)

---

## Jenkins Setup

### Plugins Installation
Ensure the following Jenkins plugins are installed for the pipeline to work seamlessly:

1. **SonarQube Scanner Plugin**  
   ![SonarQube Plugin](https://github.com/user-attachments/assets/e395be3f-1215-43f6-904f-061e111e61f2)

2. **Kubernetes Plugin**  
   ![Kubernetes Plugin](https://github.com/user-attachments/assets/8121a639-7160-4199-bac8-66fffb3f416e)

3. **Maven Plugin**  
   ![Maven Plugin](https://github.com/user-attachments/assets/b87f61a2-5d31-4d2e-bc2a-df0600664bdd)

4. **Trivy Plugin**  
   ![Trivy Plugin](https://github.com/user-attachments/assets/ebbc0c3f-19d3-46ec-b058-92a14a004efd)

### Configuring Paths
Ensure the following paths are correctly configured in Jenkins:

1. **Maven Installation Path**  
   ![Maven Installation Path](https://github.com/user-attachments/assets/6f9adae0-82ce-4371-9b42-6b7b62234189)

2. **Docker Path**  
   ![Docker Path](https://github.com/user-attachments/assets/d7eb8eb1-1cb3-4d24-9db7-6cd5fb752654)

3. **SonarQube Automatic Installation**  
   ![SonarQube Auto Install](https://github.com/user-attachments/assets/ef432367-2893-4219-9c4b-7295517aa6ec)

4. **JDK Path**  
   ![JDK Path](https://github.com/user-attachments/assets/d37f87bd-03ad-4aae-beca-762e0574714c)

---

## SonarQube Setup

### Running SonarQube Docker Image
To set up SonarQube, run the Docker container:

![SonarQube Docker Setup](https://github.com/user-attachments/assets/de81adc4-33a4-4000-b028-2122b57230c6)

Once the container is running, access SonarQube at [http://localhost:9000](http://localhost:9000). The default credentials are:

- **Username:** admin
- **Password:** admin

![SonarQube Login](https://github.com/user-attachments/assets/c0899bb8-8f18-4772-a67a-5697a4569047)

### Generating SonarQube Token for Jenkins
Once logged in, navigate to the **Administrator** section to generate a token for integration with Jenkins.

![SonarQube Token Generation](https://github.com/user-attachments/assets/a19e25ae-5afc-4bd9-9851-8be5960a7d3e)

The token will be used in Jenkins credentials to connect to SonarQube.

---

## Jenkins Integration with SonarQube

Once the token is generated, configure it in Jenkins:

1. Go to Jenkins Credentials and add the SonarQube token.
   ![Jenkins Credentials Configuration](https://github.com/user-attachments/assets/a5eb9dcc-e7ef-4b85-9d63-1c777d5be0a0)

2. The pipeline will use this token to interact with SonarQube for code analysis.

![Jenkins Configuration](https://github.com/user-attachments/assets/151cf91e-61b4-4c98-8111-5f6c0977e5bc)

---

## Jenkins Job Execution

The Jenkins job executes successfully and pushes the code to SonarQube for scanning, followed by deploying the image to Docker Hub.

### Jenkins Success
![Jenkins Success](https://github.com/user-attachments/assets/128582fc-6663-4b7d-ab61-0b3155e0348f)

### SonarQube Scan Result
![SonarQube Scan Result](https://github.com/user-attachments/assets/081e236d-6706-4f41-ab03-13cc97e2b417)

### Docker Hub Deployment
![Docker Hub Deployment](https://github.com/user-attachments/assets/2c214d27-1a96-4393-969f-4c667eb4f596)

---

## Kubernetes Deployment

Once the image is pushed to Docker Hub, the next step is deployment to Kubernetes. Below is the `kubectl` command output for the deployed application.

### Kubernetes Deployment Status
![Kubernetes Deployment](https://github.com/user-attachments/assets/582c9cf3-00ce-41d5-9298-6da892a7861b)

To access the application, forward the port using `kubectl port-forward`.

### Accessing the Web Application
![Web Application Access](https://github.com/user-attachments/assets/9b54ac13-4df9-48c2-a42e-ed0284c53dab)
