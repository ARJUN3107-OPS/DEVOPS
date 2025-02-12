# **Automate with CloudFormation**

## **Objective**
This project demonstrates the use of AWS CloudFormation to automate infrastructure provisioning and management. By defining resources in templates, we ensure consistent, scalable, and repeatable deployments.

## **How CloudFormation Was Used**
- **Automation**: I automated the deployment of resources like IAM roles, CodeBuild, S3 buckets, and more using a CloudFormation template. This eliminated manual configuration and improved infrastructure repeatability.
- **Custom Template Creation**: Used the IaC (Infrastructure as Code) generator to create the template, but some resources (like CodeCommit repositories and CodeBuild projects) had to be manually added.
- **IAM Role Creation Issue**: Initially, the IAM role failed to create due to the incorrect sequencing of policy attachment. I added a `DependsOn` attribute to ensure proper creation order.

## **Key Concepts**
- **CloudFormation Templates**: CloudFormation templates are YAML or JSON files that define AWS resources. These templates automate the provisioning and management of resources.
- **Stack**: A stack is a collection of AWS resources that CloudFormation manages together. It allows for the creation, update, and deletion of resources in a consistent and predictable manner.

## **Challenges**
- **IAM Role Creation**: I encountered an issue where IAM roles couldn't be created properly due to a policy attachment race condition. To resolve this, I added the `DependsOn` attribute, which made CloudFormation wait for the IAM role to be fully created before attaching policies.
- **Circular Dependency**: During testing, I ran into a circular dependency error due to interdependent resources. I resolved this by adjusting the order of resource creation, particularly by eliminating direct references between IAM roles and policies.

## **Resources Automated**
- **IAM Role**: CodeBuild-specific IAM role for resource provisioning.
- **S3 Bucket**: Used for storing build artifacts.
- **CodeBuild Project**: Compiles and packages the NextWork web application.
- **CodeCommit Repository**: Hosts the source code for the web application.

## **Project Time**
This project took approximately **2 hours** to complete, including troubleshooting errors and adjusting the template.

## **Final Results**
After addressing the errors and making the necessary changes to the template, I successfully created a new stack that deployed all resources correctly. I verified the resources by checking the "Resources" tab in CloudFormation.

## **Conclusion**
Using AWS CloudFormation for this project allowed me to automate infrastructure management, ensuring consistency and reducing manual errors. The experience also taught me how to handle dependencies and resource sequencing in CloudFormation templates.


