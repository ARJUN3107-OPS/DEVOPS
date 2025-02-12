# **Dependencies and AWS CodeArtifact**

## **Objective**
This project demonstrates how to integrate AWS CodeArtifact into a Java project to securely manage dependencies. I used CodeArtifact to store and manage software dependencies for my web app, connected it with Cloud9 IDE, and compiled the project.

## **What is AWS CodeArtifact?**
AWS CodeArtifact is a fully managed repository service that stores and manages software dependencies securely. It integrates seamlessly with tools like Maven and Gradle, allowing developers to simplify dependency management and improve project build processes.

## **How I Used CodeArtifact**
- **Set Up CodeArtifact**: I created a repository in AWS CodeArtifact to securely store the required dependencies and libraries for my Java project.
- **Connected to Cloud9**: I configured my Cloud9 IDE to access the CodeArtifact repository and fetch dependencies needed for my web app.
- **Managed Dependencies**: By configuring Maven’s `settings.xml`, I ensured that AWS CodeArtifact was set up as the primary repository for dependency management, simplifying the process of versioning and security.

## **Key Configuration Files**
- **settings.xml**: This Maven configuration file stores repository URLs, authentication tokens, and profile configurations. I configured it to authenticate with AWS CodeArtifact and manage dependencies securely for my web app project.

## **Testing the Connection**
I tested the connection by compiling my Java web app, which triggered Maven to fetch dependencies from CodeArtifact. After compiling, I verified that the dependencies were correctly synced, ensuring that the project had access to the necessary libraries.

## **IAM Policies for CodeArtifact Access**
I created IAM policies to define permissions for securely accessing CodeArtifact. These policies enable actions like retrieving auth tokens, accessing repository endpoints, and reading from repositories. This ensures proper access control and security.

## **Project Time**
This project took approximately **2 hours**. The majority of the time was spent setting up CodeArtifact, configuring Cloud9, troubleshooting, and fine-tuning configurations to ensure smooth dependency management.

## **Conclusion**
Integrating AWS CodeArtifact into my project simplified the management of software dependencies and allowed me to securely store and retrieve necessary libraries. This project enhanced my understanding of AWS services for secure dependency management and IAM policies.

