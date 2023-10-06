# Automating LoadBalancer configuration with Shell Scripting

- This project demonstrates load balancer configuration using shell scripting and CI/CD on Jenkins, and

also using automation process to setup and maintain load balancer.

## Automate the Deployment of Webservers

- In the previous project **`IMPLEMENTING LOADBALANCERS WITH NGINX`**, remember we deployed two backend

servers, with a load balancer distributing traffic across the webservers. Note, we did all configurations

and commands via the terminal.

Now, imagine automating the whole process. We will achieve this by writing a shell script, that when executed

all we did manually will be done automatically.

# Deploying and Configuring the Webservers

- All the process we need to deploy our webservers is the shell script below:
