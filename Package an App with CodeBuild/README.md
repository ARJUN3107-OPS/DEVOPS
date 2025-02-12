# **Packaging a Web App with AWS CodeBuild**

## **Objective**
This project demonstrates how to automate the build, test, and packaging process of a web application using AWS CodeBuild. It covers setting up CodeBuild, configuring a buildspec.yml file, and storing the final build artifact in an S3 bucket.

## **What is AWS CodeBuild?**
AWS CodeBuild is a fully managed build service that compiles source code, runs tests, and packages applications. It eliminates the need for self-managed build servers and integrates seamlessly with AWS services like CodePipeline, CodeArtifact, and S3.

## **How I Used CodeBuild**
- **Set Up an S3 Bucket**: Created an S3 bucket to store the WAR file.
- **Configured a CodeBuild Project**: Defined source, environment, artifacts, and logging configurations.
- **Wrote a buildspec.yml File**: Automated the build process using four phases.
- **Modified IAM Roles**: Ensured CodeBuild had permissions to fetch dependencies and store artifacts.
- **Ran a Build**: Compiled the code, generated a WAR file, and verified it in the S3 bucket.

---

## **Project Setup**
### **1. Setting Up an S3 Bucket**
- Created an **S3 bucket** to store the build artifact (WAR file).
- This ensures the packaged app is accessible for future deployments.

### **2. Setting Up a CodeBuild Project**
#### **Source**
- Configured CodeBuild to fetch source code from an **S3 bucket**.

#### **Environment**
- Selected a **Java runtime environment** to ensure all dependencies and tools required for building the app were available.

#### **Artifacts**
- Chose **S3** as the destination to store the final **WAR file**.

#### **Logs**
- Configured **CloudWatch Logs** to track and troubleshoot build progress.

---

### **3. Writing the buildspec.yml File**
The `buildspec.yml` file defines the build process in four stages:

#### **Install Phase**
- Defines runtime versions (e.g., Java).
  
#### **Pre-Build Phase**
- Fetches the authentication token required to access dependencies in **AWS CodeArtifact**.

#### **Build Phase**
- Runs `mvn compile` to compile the project.

#### **Post-Build Phase**
- Runs `mvn package` to generate the **WAR file**, marking the completion of the build process.

---

### **4. Modifying IAM Role for CodeBuild**
- Created a **service role** when setting up CodeBuild.
- Attached the `codeartifact-nextwork-consumer-policy`, allowing CodeBuild to fetch dependencies from **CodeArtifact**.

---

### **5. Running the Build**
- Started the build via the **AWS CodeBuild console**.
- The build process took **~5 minutes**, compiling, testing, and packaging the app.
- The final artifact, **nextwork-web-project.zip**, containing the **WAR file**, was stored in the S3 bucket.

---

## **Key Learnings**
- **Seamless Integration**: CodeBuild and CodeArtifact worked together efficiently, reducing manual dependency management.
- **IAM Configuration**: Attaching the right permissions was crucial for fetching dependencies.
- **S3 Storage**: Storing the build artifact in S3 makes deployment easier.

## **Project Duration**
- The entire setup and build process took approximately **2 hours**.

---

## **Conclusion**
Using AWS CodeBuild, I automated the entire build pipeline, eliminating manual steps and ensuring a **consistent**, **scalable**, and **reliable** build process. This project reinforced my understanding of CI/CD and AWS automation.

---

💡 **Check out more projects at** [nextwork.org](https://nextwork.org/)
