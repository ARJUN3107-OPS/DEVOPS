# 🚀 Deploying a Java Web App on AWS EC2  

## 📌 Overview  
This project sets up a **Java web app** on an **AWS EC2 instance** using **VSCode Remote - SSH**, **Maven**, and **Java**.

## ⚙️ Setup Steps  

### 1️⃣ Launch EC2 Instance  
- Created an **EC2 instance** and enabled **SSH access**.  
- Connected using:  
  ```sh
  ssh -i /path/to/key.pem ec2-user@<EC2_PUBLIC_IP>
  ```  

### 2️⃣ Install Java & Maven  
```sh
sudo yum install java-11-amazon-corretto -y  
sudo yum install maven -y
```  

### 3️⃣ Set Up VSCode  
- Installed **Remote - SSH** extension to edit files directly on EC2.  

### 4️⃣ Create a Java Web App  
```sh
mvn archetype:generate -DgroupId=com.example \
    -DartifactId=my-web-app \
    -DarchetypeArtifactId=maven-archetype-webapp \
    -DinteractiveMode=false
```  

### 5️⃣ Modify `index.jsp`  
```html
<html>
<body>
    <h2>Hello Arjun!</h2>
    <p>My NextWork web app is running!</p>
</body>
</html>
```  

## 🎯 Key Learnings  
✅ Seamless EC2 + VSCode integration  
✅ Simplified Java web app deployment  
✅ Hands-on cloud development experience  

🚀 **More projects at** [nextwork.org](https://nextwork.org/)
