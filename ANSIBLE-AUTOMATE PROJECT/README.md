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