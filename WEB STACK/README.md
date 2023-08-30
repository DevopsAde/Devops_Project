# Documentation For WEB STACK IMPLEMENTATION

This Project shows how to build and deploy web applications using the LEMP stack. It emphasis on creating dynamic and high-performing 

websites by combining Linux, Nginx, MySQL, and PHP.

Note, in the previous deployment of LAMP stack we used Putty on Windows to connect into our EC2 instance, now we going to introduce 

another method using the Git Bash erminal and SSH into it and see if it works. But first we going to create an EC2 instance, following this link to 

see the steps in creating an instance **`https://github.com/DevopsAde/Devops_Project/tree/main/LAMP%20STACK`**

Now that i have my EC2 instance created, always remember to copy this command to connect, below is the output:

![Alt text](<Images/ssh command.png>)

NOTE: Always **`cd`** change directory into where your keypair was downloaded or you will encounter an error, in this case mine is **`cd Downloads`**

Below is the output using the Git Bash:

![Alt text](<Images/Git Bash ssh.png>)

![Alt text](<Images/Git Bash ssh contd.png>)

## Installing the Nginx Web Server

To display web pages we going to install Nginx, a high performance web server. Using the command **`apt update`** package manager

 to install this package, then finally use **`apt install`** to get Nginx installed.

![Alt text](<Images/apt pkg.png>)

**`sudo apt update`** installed 113 packages

![Alt text](<Images/apt pkg cont.png>)

**`sudo apt install nginx`**

![Alt text](<Images/nginx install.png>)

![Alt text](<Images/nginx install B.png>)

![Alt text](<Images/nginx install c.png>)

To verify the status of nginx installation if everything is okay, HOLLA!!! ACTIVE AND RUNNING SUCCESSFULLY.

![Alt text](<Images/nginx status.png>)

Now, that we have launched our first Web Server into the clouds, to receive any traffic we need to open TCP port 80 

which is a default port for web browsers to access web pages on the internet. Note, TCP port 22 is open by default on 

the EC2 instance via SSH. The latter is used to open inbound connection.  

Click on security and click on edit inbound rules on the far right and input the details below and save rules.

![Alt text](<Images/edit inbound rules.png>)

Also, note the **`0.0.0.0/0`** means any IP Address can access it from anywhere.

Lets check it locally on our Ubuntu shell machine and run the command below:

**`$ curl http://localhost:80`** or **`curl http://127.0.0.1:80`** both display same outputs.

![Alt text](<Images/curl verification.png>)

Now for the finally part lets check our Nginx server can respond to requests from the internet. 

using the Public IPv4 address which in this case is **`34.255.87.229`**

### Hurray Nginx Server Works

![Alt text](<Images/nginx confirmed.png>)

#### INSTALLING MYSQL

We Previously have our Nginx Web Server up and running, now we need to install the Database Management System (DBMS) 

to store and manage data for the site in a relational database.

Using this command we installed Mysql **`sudo apt install mysql-server`**

![Alt text](<Images/mysql installation.png>)

When Prompted during installation Type **`Y`** and Hit **`Enter`**

![Alt text](<Images/press Y and hit enter.png>)

Download in Progress

![Alt text](<Images/sql download progress.png>)

After successful installation, lets login to the Mysql console with this command

**`sudo mysql`** this command connect to the MySQL server as the administrative database user root. Output below:

![Alt text](<Images/sql connect.png>)

Moving forward we have to run a security script that comes pre-installed with Mysql. The purpose of this script is to remove 

insecure default settings and lock down access to the database system. But before we proceed we set a password for the root user

using **`mysql_native_password`** as a default authentication method. In this setting we define the user password as **`PassWord.1`**

![Alt text](<Images/sql password set.png>)

Now, what follows is to start the interactive script with this commands below and steps:

![Alt text](<Images/sql validation.png>)

![Alt text](<Images/sql validation B.png>)

![Alt text](<Images/sql validation C.png>)

Now, lets see if we can login to the MySQL console by using this command **`sudo mysql -p`** note the **`-p`** flag is used to prompt 

for the password used after the changing the **`root`** user password **`PassWord.1`**

Hurray what this means is that password was set, and changed successfully.

![Alt text](<Images/mysql console connect.png>)

Now that my Mysql server is set up and running we move to the setting up and installing PHP.

## Installing PHP

Now that we have Nginx installed to serve content and Mysql installed to store and manage data. We now have to install PHP to process code 

and generate dynamic content for the web server. Now to note the difference **`APACHE`**` embeds the PHP interpreter in each request, 

**`NGINX`** requires an external program to handle PHP processing which act as a bridge between the PHP interpreter and the web server. 

We need to install **`php-fpm`** which stands for **`PHP FastCGI process manager`**, this tells Nginx to pass PHP requests to this software for 

processing. Also, we will need **`php-mysql`**, a PHP module that allows PHP to communicate with Mysql-based Databases.

We need to install this 2 packages at once, command below:

**`sudo apt install php-fpm php-mysql`**

When Prompted enter **`Y`** and Hit **`Enter`**

![Alt text](<Images/package dependencies.png>)

Successful Download in Progress

![Alt text](<Images/dependencies install progress.png>)

Now that we have the PHP components installed we now have to configure Nginx to use them.

## Configuring Nginx to Use PHP Processor