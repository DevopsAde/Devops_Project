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

- Install Ansible using the command **`sudo apt install ansible`**

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
- Let's check the ansible version we running use this command **`ansible --version`**

![Alt text](Images/ansible_version.png)

- And also check the status of the Jenkins **`sudo systemctl status jenkins`** && NOTE: to restart use **sudo systemctl restart jenkins.service`**

![Alt text](Images/jenkins_status.png)

- Note, for us to use Jenkins we have to edit inbound rules on the security group. **`Jenkins uses PORT 8080`**

![Alt text](Images/jenkins_security_edit_inbound.png)

- Now click on the public IP Address and type it like this followed by the port number **`http://54.154.130.55:8080/`**

![Alt text](Images/jenkins_IP.png)

- Now to unlock Jenkins below after pasting the **`url`** followed by port **`8080`**. Use **`sudo cat /var/lib/jenkins/secrets/initialAdminPassword`**

![Alt text](Images/jenkins_unlock.png)
![Alt text](Images/Jenkins_secret_PASS.png)

- Copy the HASH PASSWORD to unlock Jenkins.

![Alt text](Images/paste_hash_jenkins.png)
![Alt text](Images/Jenkins_pass_accepted.png)

- Click to install Suggested Plugins



2. In your GitHub account create a new repository and name it **`ansible-config-mgt`**

![Alt text](Images/ansible-config-mgt.png)

- Now let's initialize a git repo where we have **`ansible-config-mgt`**, remember to open it with **`VSCODE`** and run the following command below:

```$ echo "# ansible-config-mgt" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/DevopsAde/ansible-config-mgt.git
git push -u origin main
```
![Alt text](Images/ansible_conf_readme.png)

- Create a new Freestyle project **`ansible`** in Jenkins and point it to your 'ansible-config-mgt' repository.

1. **`Skip and continue as admin`** && **`Save and Continue`**

![Alt text](Images/jenkins_click_1.png)
![Alt text](Images/jenkins_click_2.png)
![Alt text](Images/jenkins_ready.png)

![Alt text](Images/create_JOB.png)
![Alt text](Images/create_freestyle_project.png)


- Configure a webhook in GitHub and set the webhook to trigger **`ansible`** build.

![Alt text](Images/webhook.png)
![Alt text](Images/create_webhook.png)

- Now we want jenkins to communicate with GitHub we paste **`http://54.154.130.55:8080/`** of jenkins in the field followed by **`github-webhook/`**

- And change the **`Content type`** to **`application/json`**

![Alt text](Images/jenkins_communicate.png)
![Alt text](Images/webhook_success.png)

- Configure a Post-build job to save all (**) files.

1. Specify the source code management. Copy the webhook url **`https://github.com/DevopsAde/ansible-config-mgt`**

![Alt text](Images/source_code_mgt.png)

![Alt text](Images/post_build_tick.png)

- On the Post-Build option select **`Artifacts`**

![Alt text](Images/select_artifacts.png)

- And type **`**`** wildcard to save all files && Click **`Apply`** && **`Save`**.

![Alt text](Images/Apply_wildcard.png)

2. Test the setup by making some changes to the **`README.md`** file in **`main`** branch and make sure that builds starts automatically and Jenkins

saves the files (build artifacts) in the following folder **`ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/`**

![Alt text](Images/readme_changes_text.png)
![Alt text](Images/build_archive_history.png)
![Alt text](<Images/build_config success.png>)
![Alt text](Images/build_output.png)







