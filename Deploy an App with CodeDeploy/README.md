# **Deploying a Web App with AWS CodeDeploy**

## **Objective**
This project demonstrates how to automate the deployment of a web application to an AWS EC2 instance using AWS CodeDeploy. It covers setting up an EC2 instance, configuring deployment scripts, managing dependencies, and deploying the app efficiently.

## **What is AWS CodeDeploy?**
AWS CodeDeploy is a fully managed deployment service that automates software deployments across compute platforms such as EC2 instances, on-premises servers, and Lambda functions. It ensures consistent deployments, reduces errors, and enables easy rollbacks.

## **How I Used CodeDeploy**
- **Created an EC2 Instance**: Launched an EC2 instance inside a Virtual Private Cloud (VPC) using AWS CloudFormation.
- **Set Up a Deployment Group**: Defined a deployment group to manage the target EC2 instances for deployment.
- **Wrote Deployment Scripts**: Created Bash scripts to install dependencies, start/stop services, and ensure smooth deployment.
- **Configured IAM Roles**: Defined IAM roles and policies to grant CodeDeploy the necessary permissions.
- **Deployed the Application**: Uploaded the app to an S3 bucket and used CodeDeploy to fetch and install it on the EC2 instance.

## **Project Setup**
### **1. EC2 Instance & VPC**
- Launched an EC2 instance inside a VPC to securely host the web application.
- Used AWS CloudFormation to automate provisioning.
- Chose separate environments for **production** and **development** to ensure stability.

### **2. Bash Deployment Scripts**
I created three key scripts to manage deployment:

#### **install_dependencies.sh**
- Installs **Apache HTTPD** and **Tomcat**.
- Configures Apache to forward requests to Tomcat.
- Ensures necessary dependencies are installed.

#### **start_server.sh**
- Starts **Apache HTTPD** and **Tomcat** services.
- Ensures the services restart automatically on system reboot.

#### **stop_server.sh**
- Stops existing Apache and Tomcat services before deploying the new version.
- Ensures clean deployment by preventing conflicts with running services.

### **3. IAM Role for CodeDeploy**
- Created a custom **IAM service role** for CodeDeploy.
- Assigned permissions for managing EC2 instances and handling deployments.
- Allowed actions like retrieving revision files from S3 and running deployment scripts.

### **4. CodeDeploy Configuration**
- Created a **CodeDeploy application** that defines the deployment process.
- Chose **EC2** as the compute platform.
- Set up a **deployment group** to target specific EC2 instances.

### **5. Deployment Process**
- **Revision Location**: Stored application files in an **S3 bucket**.
- **Deployment Execution**: CodeDeploy fetched the code, executed deployment scripts, and started the app on EC2.
- **Testing**: Verified the deployment by visiting the EC2 **public IP** or **domain name** in a browser.

## **Key Learnings**
- Managing dependencies between **Apache HTTPD and Tomcat** required careful configuration.
- CodeDeploy automates deployments but requires proper IAM permissions and agent setup.
- CloudFormation helped streamline the setup of EC2 instances and networking.

## **Project Duration**
This project took approximately **2 hours**, including setting up AWS services, writing scripts, and troubleshooting issues.

## **Conclusion**
Using AWS CodeDeploy streamlined the deployment process, ensuring a **consistent**, **automated**, and **scalable** approach for deploying web applications. This project improved my understanding of CI/CD pipelines, AWS services, and infrastructure automation.

---

💡 **Check out more projects at** [nextwork.org](https://nextwork.org/)
