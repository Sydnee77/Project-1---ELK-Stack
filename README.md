## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Diagram](https://github.com/Sydnee77/Project-1---ELK-Stack/blob/main/Diagrams/Homework%2313_Project%231.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

# My Playbook Files

- [DVWA Playbook](https://github.com/Sydnee77/Project-1---ELK-Stack/blob/main/Ansible/DVWA.yml)
- [Filebeat Configuration](https://github.com/Sydnee77/Project-1---ELK-Stack/blob/main/Ansible/filebeat-configuration.yml)
- [Filebeat Playbook](https://github.com/Sydnee77/Project-1---ELK-Stack/blob/main/Ansible/filbeat-playbook.yml)
- [metricbeat Configuration](https://github.com/Sydnee77/Project-1---ELK-Stack/blob/main/Ansible/metricbeat-configuration.yml)
- [metricbeat Playbook](https://github.com/Sydnee77/Project-1---ELK-Stack/blob/main/Ansible/metricbeat-playbook.yml)

## This document contains the following details:

- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

#### What aspect of security do load balancers protect? 
Load balancer protects the system from DDoS attacks by sending the traffic somewhere else.
#### What is the advantage of a jump box? 
To give secure access to SSH and Private keys.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
#### What does Filebeat watch for? 
Fiberbeat monitors log files which are the locations that collects the events of the logs and forwards them for indexing,
#### What does Metricbeat record?
Metricbeats helps monitors the server by collecting the metrics from the system and services to the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |20.9.24.163 | Linux            |
| ELK Stack| Gateway  | 10.0.0.8   | Linux            |
| Web-1    | LBlancer | 10.0.0.5   | Linux            |
| Web-2    | LBlancer | 10.0.0.6   | Linux            |
| Web-3    | LBlancer | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

#### Only the Elk machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
IP addresses 10.0.0.8

Machines within the network can only be accessed by Jumpbox through the SSH Private Key.
#### Which machine did you allow to access your ELK VM? 
Jumpbox

#### What was its IP address? 
20.9.24.163

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
#### What is the main advantage of automating configuration with Ansible? 
Configuration and application 

#### The playbook implements the following tasks:
In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
1. Check to see if there is Docker to install and update
2. Check to see if there is python3 to install and update
3. Install the the Docker
4. Increase the virtual memory
5 Download and launch the Docker Elk Container

#### The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

#### Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
docker_ps_output.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
#### List the IP addresses of the machines you are monitoring
10.0.0.5
10.0.0.6
10.0.0.7

#### We have installed the following Beats on these machines: 
Webservers

#### Specify which Beats you successfully installed: 
Data shippers to Logstash filter and transform to Elasticsearch

#### In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
The Beats allow us to collect machine health, performance, system logs, events and so on from each machine.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

#### SSH into the control node and follow the steps below:
- Copy the filebeat file to file-conifig.yml.
- Update the filebeat.yml file to include...
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

#### Answer the following questions to fill in the blanks:
Which file is the playbook? Ansible-playbook files 
Where do you copy it? Root of ansible
Which file do you update to make Ansible run the playbook on a specific machine? Hosts configuration file
How do I specify which machine to install the ELK server on versus which to install Filebeat on? HostName in the Host configuration file
Which URL do you navigate to in order to check that the ELK server is running? SSH azadmin@10.0.0.5 Web-1

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

