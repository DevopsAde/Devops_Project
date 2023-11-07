# ANSIBLE REFACTORING AND STATIC ASIGNMENTS (IMPORTS AND ROLES)

In this project we will continue working with **`ansible-config-mgt`** repository and make some improvements to the code. Now we need to

refactor the ansible code, create assignments, and learn how to use the imports functionality. Imports allow to effectively re-use previously

created playbooks in a new playbook. It allows us to organize tasks and reuse them when needed.

# Side Self Study: For better understanding or Ansible Artifcats re-use- [read this article](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse.html)

## Code Refactoring

Refactoring is a general term in computer programming. It means making changes to the source code without changing expected behaviour 

of the software.

The main idea of refactoring is to enhance code readability, increase maintainabilityand extensibility, reduce complexity, add proper 

comments without affecting the logic.

In this case, we will move things around a little bit in the code, but the overall state of the infrastructure remians the same.

Let us see how we can improve our Ansible Code!

# Refactor Ansible Code by Importing other playbooks into site.yml

Step 1 - Jenkins Job Enhancement

Before we begin, let us make some changes to our Jenkins job - now every new change in the codes creates a seperate directory which is not very convenient

when we want to run some commands from one place. Besides, it consumes space on Jenkins server with each subsequent change. Let us enhance it by introducing a 

new Jenkins project/job - we will require **`copy Artifact`** plugin

1. Go to your **`Jenkins_ansible`** server and create a new directory called **`ansible-config-artifact`** - we will store there all artifacts after each build.

**`sudo mkdir /home/ubuntu/ansible-config-artifact`**

2. Change permissions to this directory, so Jenkins could save files there - **`chmod -R 0777 /home/ubuntu/ansible-config-artifact`**

3. Go to the Jenkins web console -> Manage Jenkins -> Manage Plugins -> on Available tab search for Copy Artifact and install this plugin without restarting Jenkins