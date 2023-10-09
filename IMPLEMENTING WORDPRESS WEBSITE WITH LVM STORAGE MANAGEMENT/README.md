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

- **In this 3-Tier Setup, prerequiste required below**:

1. A Laptop or PC to serve as a client

2. An EC2 Linux Server as a Web Server (This is where we will install WordPress)

3. An EC2 Linux Server as a Database (DB) server

# NOTE:

- We going to use **`RedHat`** OS for this project, remember for Ubuntu server we connect via SSH/Putty or any other tool

we use **`Ubuntu`** user, but for RedHat we will need to use **`ec2-user`** user. Connection string will look like this

**`ec2-user@<Public-IP>`**

## Implementing LVM on Linux Servers(Web and Databse Servers)

- Step 1: Prepare a Web Server

1. Launch an EC2 instance that will serve as WebServer. Create 3 volumes in the same Availability Zone as the WebServer 

EC2, each of 10 GiB

![Alt text](Images/web_server.png)
*Web_server_WordPress*

![Alt text](<Images/volumes created.png>)
*Three of 10 GiB Volumes each created, availability zone eu-west-1a same with the EC2 instance*

2. Attach all three volumes one by one to the Web_server_WordPress EC2 Instance Created.

![Alt text](<Images/attach volume.png>)

*Volumes Attached*

# NOTE: All volumes attached and ready in-use in the screenshot below:

![Alt text](Images/Volumes_successfully.png)

3. Open up the Linux Terminal to Begin Configuration and use **`lsblk`** command to inspect what block devices

are attached to the server.

*Newly Created Devices*

![Alt text](<Images/list of disk.png>)

- Note, all devices in Linux reside in **`dev/directory`**. Inspect it with the command **`ls /dev/`**. The 3 newly

created block devices will be **`xvdf`**, **`xvdh`**, **`xvdg`**.

![Alt text](<Images/ls dev.png>)

4. Use **`df -h`** command to see all mounts and free space on the server.

![Alt text](<Images/chk free_space.png>)

5. Use **`gdisk`** utility to create a single partition on each of the 3 disks. Use this 

command **`sudo gdisk /dev/xvdf`**, **`/xvdg`**, **`/xvdh`**. Successful Screenshot below:

![Alt text](Images/xvdg.png)

*xvdg Partitioning*

![Alt text](Images/xvdh.png)

![Alt text](<Images/xvdh cont..png>)

*xvdh Partitioning*

6. Now use **`lsblk`** utility to view the newly configured partition on each of the disks.

- Check out the output below for newly created partitions on each devices.

![Alt text](Images/partitions.png)

*Partitions Created*

7. Install **`Ivm2`** package using **`sudo yum install Ivm2`**.

![Alt text](<Images/yum install lvm2.png>)

- HIT **`y`** and **`ENTER`** to Install. Then, run **`sudo lvmdiskscan`** command to check for available partitions.

![Alt text](<Images/check diskscan.png>)

- NOTE: We using **`yum`** to install packages because we using the RedHat/CentOS not Ubuntu which is **`apt`**.

8. Now, use **`pvcreate`** utility to mark each of the 3 disks as physical volumes to be used by LVM.

![Alt text](Images/pvcreate.png)

9. Lets now verify if the physical volume has been created successfully by using the command **`sudo pvs`**

![Alt text](Images/pvs.png)