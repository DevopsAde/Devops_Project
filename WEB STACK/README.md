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

 to install this package, then finally use **`apt`** install to get Nginx installed.

![Alt text](<Images/apt pkg.png>)

**`sudo apt install`** installed 113 packages

![Alt text](<Images/apt pkg cont.png>)

![Alt text](<Images/nginx install.png>)

![Alt text](<Images/nginx install B.png>)

![Alt text](<Images/nginx install c.png>)