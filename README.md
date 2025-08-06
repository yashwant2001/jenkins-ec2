Here's a `README.md` file documenting the setup process you've outlined, formatted for clarity and usability:

---

## 📦 Prerequisites

- RHEL/CentOS system
- `sudo` access
- Internet connection

---

## 🔧 Step-by-Step Installation

### 1. System Update

```bash
sudo yum update -y
````

---

### 2. Install Git

```bash
sudo yum install git -y
git --version
```

Configure Git (replace with your GitHub username and email):

```bash
git config --global user.name "github_username"
git config --global user.email "email"
git config --list
```

---

### 3. Install Docker

```bash
sudo yum install docker -y
sudo systemctl start docker
sudo systemctl enable docker
```

---


### 5. Search and Install Java 21

```bash
sudo yum search java -17
sudo yum search java -21
sudo dnf install java-21-amazon-corretto -y
java --version
```

---

### 6. Install Maven

```bash
sudo yum install maven -y
mvn -v
```

---

### 7. Add Jenkins Repository and Key

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

---

### 8. Upgrade System Packages

```bash
sudo yum upgrade -y
```

---

### 9. Install Jenkins

```bash
sudo yum install jenkins -y
jenkins --version
```

---

### 10. Enable Docker Access for Jenkins

```bash
sudo usermod -aG docker jenkins
```

---

### 11. Start and Enable Jenkins

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

---

### 12. Get Jenkins Initial Admin Password

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Use this password to unlock Jenkins through the web interface at:

```
http://<your_server_ip>:8080
```

---

## ✅ Jenkins Setup Complete!

You can now continue with plugin installation and pipeline configuration via the Jenkins UI.




