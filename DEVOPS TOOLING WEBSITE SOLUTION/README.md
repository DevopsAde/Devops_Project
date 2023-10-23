# Devops Tooling Website Solution

In this project we going to explore the integration of various tools and technologies to create a unified platform

that enhances collaboration, automation, and efficiency for software development and operations teams.

- NOTE: In the just concluded project **`IMPLEMENTING WORDPRESS WEBSITE WITH LVM STORAGE MANAGEMENT`**, we implemented

a WordPress based solution filled with content, which can be used as a full fledged website or blog.

Now, to expantiate further we will add some more value to the solutions that the DevOps team can utilize. This includes

introducing a set of DevOps tools that will help our team in day to day activities in managing, developing, testing,

deploying and monitoring different projects.

## TOOLS

The tools we want our team to use are widely used by multiple DevOps teams.

- Jenkins - Free and open source automation server used to build **`CI/CD`** pipelines.

- Kubernetes - An open-source container-orchestration system for automating computer application deployment, scaling and management.

- Jfrog Artifactory - Universal Repository Manager supporting all major packaging formats, build tools and CI servers.

- Rancher - An open source software platform that enables organizations to run and manage Docker and Kubernetes in production.

- Grafana - A multi-platform open source analytics and interactive visualization web application.

- Prometheus - An open-source monitoring system with a dimensional data model, flexible query language, efficient time series

database and modern alerting approach.

- Kibana - Kibana is a free and open user interface that lets you visualize your Elasticsearch data and navigate the Elastic Stack.

## In this project we going to implement a solution that consists of the following components:

1. Infrastructure: AWS

2. Webserver Linux: RedHat Enterprise Linux 8

3. Database Server: Ubuntu 20.04 + MySQL

4. Storage Server: RedHAt Enterprise Linux 8 + NFS Server

5. Programming Language: PHP

6. Code Repository: GitHub

- NOTE: For Rhel 8 server use this ami------------------

The diagram below comprises of several stateless Web Servers that share a common database and also access the same files using

Network File System (NFS) as a shared file storage. Despite the NFS server been located on a completely separate hardware, for Web Servers

it looks like a local file system from where they can serve the same files.

![Alt text](<Images/3tier web application.png>)

It is important to know what storage solution is suitable for what use cases. Questions like: what data will be stored, in what format

how this data will be accessed, by whom, from where, how often, etc. Base on this we will be able to choose the right storage system

for our solution.

## IMPLEMENTING A BUSINESS WEBSITE USING NFS FOR THE BACKEND FILE STORAGE

- Step 1: Prepare NFS Server

1. Spin up a new EC2 instance with RHEL Linux 8 operating system.

2. Based on the LVM experience from the [3-tier architecture project], ![A](https://github.com/DevopsAde/Devops_Project/tree/main/IMPLEMENTING%20WORDPRESS%20WEBSITE%20WITH%20LVM%20STORAGE%20MANAGEMENT)
