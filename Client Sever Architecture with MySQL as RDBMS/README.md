# Understanding Client Server Architecture with MySQL as RDBMS

- In this topic we going to gain a comprehensive understanding of data management, connectivity, and communication

between clients and servers.

First let's define what actually a Client and Server is?

- Client: A client is a user or system that requests a specific resource or service from another entity know as server

**WHILE**

- SERVER: Is a resource or service provider that listens for incoming requests from clients and responds to those requests.                                        

## Client-Server Architecture with MySQL

*What is Client-Server Architecture* : Client-Server refers to an architecture in which two or more computers

are connected together over a network to send and receive requests between one another.

- Example: **`MACHINE A`** sending requests is called CLIENT & **`MACHINE B`** responding (serving the request) is called SERVER. 

Below is an explanatory diagram of a Client and Server Requests and Responses and examples of client-server applications.

![Alt text](Images/client-server-network.png)
**`source: zenarmor.com/docs/network-basics/what-is-client-server-network`**

NOTE: The client system trys to access the Website using the Web browser and sends HTTP requests to a Web server 

(Apache, Nginx, IIS or any other) over the internet.

Now, if we dive further by adding a Database Server we get a sample architecture below:

![Alt text](<Images/client-server db.png>)

Lets analyse what's happening in the diagram above. In this case, the Web Server acts has a "Client" which connects and

reads/writes to/from a Database (DB) server (MySQL, MongoDB, Oracle, SQL Server or any other), note, the communication between them 

happens over a Local Network or Internet Connection (it's a common practice to place the Web Server and DB Server close to each other 

in the local network).

- Example of a Client-Server Communication in action, here we would open our Ubuntu System or Windows Terminal 

and run the **`curl`** command.

**NOTE**: The Ubuntu does not have the **`curl`**, so we install it running **`sudo apt install curl`**

![Alt text](<Images/curl cmd.png>)

In this example, the Ubuntu terminal is the **client**, while **`www.propitixhomes.com`** will be the **server**.

Now, that we have the **`curl`** command installed, lets re-run the **`curl -Iv www.propitixhomes.com`**. 

- Output below: This shows the requests from the URL are being collected from a computer with an IP address

of **`75.2.115.196`** on port **`80`**.

![Alt text](<Images/curl www.png>)

Alternatively, another way to get a server's IP address is to use a diagnostic tool called **`PING`**. This will show 

round-trip time, time for packets to go to and back from the server. Note, this tool uses **`ICMP PROTOCOL`**.

## IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MySQL DATABASE MANAGEMENT SYSTEM (DBMS)

In this section, we going to implement a Client Sever Architecture using MySQL Database Management System (DBMS).

We going to demonstrate a basic client-server using MySQL RDBMS, by Create and Configuring two Linux-based virtual 

servers (EC2 instances in AWS). **`Server A name - mysql-server`** and **`Server B name - mysql-client`**







