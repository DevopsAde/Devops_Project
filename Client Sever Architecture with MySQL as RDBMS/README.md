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

reads/writes to/from a Database (DB) server (MySQL, MongoDB, Oracle, SQL Server or any other), note, the communication

between them happens over a Local Network or Internet Connection(it's a common practice to place the Web Server and DB Server close to each other in the local network).



