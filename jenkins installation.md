# Lab 1: Install Jenkins

### Task-0: The first step is to `Manually Launch an EC2 Server` with the below configuration:

* **Region:** North Virginia (us-east-1).
* **Use tag Name:** `CICDLab-YourName`
* **AMI Type and OS Version:** `Ubuntu 24.04 LTS`
* **Instance type:** `t2.micro`
* Create a new Keypair with the Name `CICDLab-Keypair-YourName`
* In security groups, include ports `22 (SSH)` , `80 (HTTP)` and `8080 (jenkins)`
* **Configure Storage:** 10 GiB
* Click on `Launch Instance.`

### Task-1: Install Java
Once the Anchor EC2 server is up and running, SSH into the machine using `Instance Connect` with the username `ubuntu` and do the following:
```
sudo hostnamectl set-hostname CICDLab
bash
```
```
sudo apt update
```
```
sudo apt install wget unzip -y
```
```
sudo apt install fontconfig openjdk-17-jre
```
```
java -version
```
### Task-2: Install Jenkins

```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc   https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```
```
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]"   https://pkg.jenkins.io/debian-stable binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
```
```
sudo apt-get update
```
```
sudo apt-get install jenkins
```
```
sudo systemctl enable jenkins
```
```
sudo systemctl start jenkins
```
```
sudo systemctl status jenkins
```
