# Ansible Configuration Management 

- In this project we are going to experience the power of automation with Ansible by simplifying complex tasks and streamlining 

an IT infrastructure.

- What is Ansible?

Ansible is an open-source software platform utilized for automating configuration management. It is renowned for its scalability, flexibility, and

ease of use, and is widely used in various industries such as finance, healthcare, and technology. 

In 2015, it was acquired by Red Hat, Inc. and has since become one of the leading automation tools in the market.

It uses YAML, a simple and powerful language for describing automation tasks declaratively, which makes it easy to understand and maintain.

- In the following link Below, Click and read about Ansible, **`it's uses`**, **`How Ansible Works`**, **`Ansible Playbook Example`**

[What is Ansible in DevOps and How it Works](https://kodekloud.com/blog/ansible-in-devops/)

# Ansible Client as a Jump Server (Bastion Host)

- A Jump Server (sometimes also referred as Bastion Host) is an intermediary server through which access to internal network can be provided. 

If you think about the current architecture you are working on, ideally, the webservers would be inside a secured network which cannot be reached 

directly from the Internet. That means, even DevOps engineers cannot SSH into the Web servers directly and can only access it through a Jump Server.

It provide better security and reduces attack surface. On the diagram below the Virtual Private Network (VPC) is divided into two subnets.

Public subnet has public IP addresses and Private subnet is only reachable by private IP addresses.

![Alt text](Images/VPC.png)

## TASKS:

- Install and configure Ansible Client to act as a Jump Server/Bastion Host

- Create a simple Ansible playbook to automate servers configuration

# Install and Configure Ansible on EC2 Instance

- Step 1: 

1. Update the **`Name`** tag on your **`Jenkins`** EC2 instance to **`Jenkins_Ansible`**. We will use this server to run playbooks.

![Alt text](Images/Name_tag_jenkins.png)

- Run **`sudo apt update -y`** to update packages and releases.

- Go to **`Jenkins.io`** and select **`Ubuntu OS`** to install open JDK requirements to install Jenkins [Jenkins Package](https://pkg.jenkins.io/debian/)

- Use this code below:

![Alt text](Images/jenkins_install_pckg.png)

- Now install the latest Jenkins [Install Jenkins](https://www.jenkins.io/doc/book/installing/linux/)

```sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

2. In your GitHub account create a new repository and name it **`ansible-config-mgt`**

3. Install Ansible using the command **`sudo apt install ansible`**

