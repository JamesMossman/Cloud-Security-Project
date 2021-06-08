## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!(/Diagrams/Azuremap.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yamal file may be used to install only certain pieces of it, such as Filebeat.

  - !(/Ansible/ansible-config.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- What aspect of security do load balancers protect? What is the advantage of a jump box?
-   The load balancer protects the availiblity of the network. The advantage of using a jump box is that you can write yml file to make changes to mulitple servers at once. This increases security by only allowing access to the web servers through the jumpbox.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the configurations and system logs.
- What does Filebeat watch for? Monitors linux logins, SSH logins, and sudo commands.
- What does Metricbeat record? Monitors for CPU usage, RAM usage, and network usage.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web1     | Webserver| 10.0.0.9    |Linux                  |
| Web2     | Webserver| 10.0.0.10   |Linux                  |
| Web3     | Webserver| 10.0.0.11  |Linux                  |
| ELK Server| SIEMS   | 10.1.0.1           |Linux                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- My personal IP Address

Machines within the network can only be accessed by the Jumpbox.
- Which machine did you allow to access your ELK VM? 
    - The Jumpbox VM
- What was its IP address?
    - 10.0.0.1

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No              | My personal IP address   |
|    Web1  | Yes                    |       10.0.0.1            |
|   Web2       |    yes             |       10.0.0.1           |
|   Web3       |      yes           |       10.0.0.1            |
|   ELK Server  |        no         |       10.0.0.1           |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- This is done so that you don't have to indvidually update every server.

The playbook implements the following tasks:
- Install Docker
- Install Pip3
- Install Docker python module
- Enable Docker when machine starts
- 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

!!(/Diagrams/ELK-Container.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.9
10.0.0.10
10.0.0.11
We have installed the following Beats on these machines:
- Filebeat
- Metricbeat 

These Beats allow us to collect the following information from each machine:
- Filebeat is able to monitors linux logins, SSH logins, and sudo commands. This a crucial element in security that can track if any threats have tried to gain access to the servers.
- Metricbeat is able to monitors for CPU usage, RAM usage, and network usage. This is usefull as we can see if any Denial of Service or similar attacks were made against the system.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the yml file to /etc/anisble/files.
- Update the yml file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- Which URL do you navigate to in order to check that the ELK server is running?
"ELK server public IP":5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._