# 🚀 End-to-End DevOps Pipeline with Harness, Terraform, Kubernetes, and GCP

This project demonstrates a complete DevOps pipeline using **Harness**, integrated with **SonarQube**, **Docker**, **Trivy**, **Terraform**, and **Kubernetes** on **GCP**, to deploy a Java-based **Calculator web application**.

---

## 📁 Repository

🔗 [Harness-end-to-end GitHub Repo](https://github.com/Saicharan619/Harness-end-to-end.git)

---

## 📌 Overview

This project is broken into **3 key stages**:

### 1️⃣ CI (Continuous Integration) – Harness CI
- Clone code from GitHub
- Run `mvn clean install`
- SonarQube quality gate analysis
- Build Docker image with `build number` as tag
- Push Docker image to Docker Hub
- Perform Trivy scan for vulnerabilities

### 2️⃣ IAC (Infrastructure as Code) – Terraform
- Create GKE cluster on GCP using `google_container_cluster`
- Install **Harness Delegate** into the cluster using Terraform module
- Fetch GKE credentials dynamically using `google_container_cluster` + `google_client_config`
- Configure Kubernetes and Helm providers dynamically

### 3️⃣ CD (Continuous Deployment) – Harness CD
- Deploy the Calculator app using `calculator-deployment.yaml`
- Expose the application via a **LoadBalancer** service
- Apply **RollingUpdate** strategy to ensure zero downtime

---

## 🔧 Tech Stack

| Tool          | Purpose                            |
|---------------|------------------------------------|
| **Harness**   | CI/CD pipeline orchestration       |
| **Maven**     | Java project build tool            |
| **SonarQube** | Static code analysis               |
| **Docker**    | Containerization                   |
| **Docker Hub**| Image repository                   |
| **Trivy**     | Vulnerability scanning             |
| **Terraform** | Infrastructure provisioning        |
| **GCP**       | Cloud provider (GKE cluster)       |
| **Kubernetes**| Container orchestration            |
| **Helm**      | (Optional) Kubernetes package management tool |

---

## 📂 Project Structure
Harness-end-to-end/
├── src/ # Java source code
├── Dockerfile # Docker build file
├── pom.xml # Maven configuration
├── README.md # Project documentation
├── Values.yaml # Helm values (if needed)
├── delegate.tf # Harness Delegate deployment via Terraform
├── deployment.yaml # Kubernetes manifest
├── main.tf # Terraform config for GKE
├── provider.tf # GCP & K8s provider configs
├── variable.tf # Input variables

---

## 📎 Final Output

The **Calculator web app** is deployed on a GKE cluster using the full DevOps pipeline. It is accessible via an external IP provided by the **LoadBalancer** service in GKE. The app performs basic arithmetic calculations, and you can interact with it through your browser.

---

## 🙋‍♂️ Author

**Sai Charan Reddy Dontiri**  
🔗 [LinkedIn](https://www.linkedin.com/in/saicharanreddydontiri/)

---
