# Implementing Wordpress Website with Logical Volume Management

## Understanding 3 Tier Architecture

- What is WordPress:

WordPress is a free and open-source content management system written in PHP and paired with **`MySQL`** or **`MariaDB`**

as its backend Relational Database Management System (RDBMS)

- Web Solution With WordPress

In this project we will provision storage infrastructure on two Linux Servers and Implement a Basic Web Solution using

**`WordPress`**. To elaborate further, this Project comprises of two parts:

- Configure Storage Subsystem for Web and Database Servers based on Linux OS (Working with disks, partitions and volumes in Linux)

- Install WordPress and connect it to a remote MySQL database server. (Deploying Web and DB tiers of Web solution)

- Three-tier Architecture

*Three-tier Architecture* is a client-server software architecture, which is generally a web, or mobile solutions. It comprises 

of 3 seperate layers.

![Alt text](Images/three-tier-architecture.png)

*Three-tier Architecture*

1. **`Presentation Layer (PL)`**: This is the user interface such as the client server or browser on your laptop.

2. **`Business Layer (BL)`**: This is the backend program that implements business logic. Application or Webserver.

3. **`Data Access or Management Layer (DAL)`**: This is the layer for computer data storage and data access. **`Database Server`**

or File System Server such as **`FTP Server`** or **`NFS Server`**

- In this project, we will showcase **Three-tier Architecture** ensuring that the disks used to store files on the Linux servers

are adequately partitioned and managed through programs such as **`gdisk`** and **`LVM`** respectively.

-  **In this 3-Tier Setup, prerequiste required below**:

1. A Laptop or PC to serve as a client

2. An EC2 Linux Server as a Web Server (This is where we will install WordPress)

3. An EC2 Linux Server as a Database (DB) server

# NOTE:

- We going to use **`RedHat`** OS for this project, remember for Ubuntu server we connect via SSH/Putty or any other tool

we use **`Ubuntu`** user, but for RedHat we will need to use **`ec2-user`** user. Connecttion string will look like this

**`ec2-user@<Public-IP>`**

