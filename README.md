# Elk-Project
UofU student first VNET Elk stack project


The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1E_OCDZwJd6Y5ly6Iw3GLI3Is8G2y8LHS/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.


This document contains the following details:

- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly **Secure**, in addition to restricting **overload** to the network.

**Load balancers ensure equal distribution of traffic flow used to help minimaize the possiblility of overwhelming a network. By using a jump box provisioner as a starting point this helps reduce the potential points of unauthorized network access. Also Jump box provisioners allow easy distribution of network management and maintainence from a single point. Used in tandom with other programs eliminates time consumption and redundancy of install and maintainence along with added security. **

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the **network traffic** and system **vulnerabilities**.

-**Filebeat is used to monitor the log files or specific locations that have been specified**.
-**Where as Metricbeat is used to store the actual metrics and statistics in easy to use and read formats**

The configuration details of each machine may be found below.

| Name     | Function |   IP Address  | Operating System |
|----------|----------|---------------|------------------|
| Jump Box | Gateway  | 52.146.88.550 | Linux            |
| Web-1    |   VNET   |   10.0.0.5    | Linux / DVWA     |
| Web-2    |   VNET   |   10.0.0.6    | Linux / DVWA     |
| Web-3    |   VNET   |   10.0.0.7    | Linux / DVWA     |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the **Jump-Box Gateway** machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
**24.11.XXX.XXX** Public IP address

Machines within the network can only be accessed by **SSH connections allowed by admin**.

**The ELK Stack VNET VM is only allowed to be accessed by SSH from the Jump-Box Gateway device. (52.146.88.350:5601)**

A summary of the access policies in place can be found in the table below.

| Name      | Publicly Accessible | Allowed IP Addresses |
|-----------|---------------------|----------------------|
| Jump Box  |         Yes         |    24.11.XXX.XXX     |
|   Web-1   |         No          |    52.146.88.50      |
|   Web-2   |         No          |    52.146.88.50      |
|   Web-3   |         No          |    52.146.88.50      |
| ELK Stack |         No          |     40.86.101.4      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

**It provides easy automation for network wide deployment after innitial set up. Allowing for efficiency and integrity to be applied to the whole network via a singular starting point**

The playbook implements the following tasks:

**Step 1: Install Dependencies.** 

**Step 2: Add Repository.**

**Step 3: Install Docker.**

**Step 4: Install Kibana.**

**Step 5: Install DVWA.**

**Step 6: Install Filebeat.**

**Step 7: Install Metricbeat.**

**Step 8: . . . Profit?**

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://docs.google.com/document/d/1fB5bPdb-ASxr8hsOwa0UMfawAdvxXNnvnuMlPqg15yk/edit?usp=sharing

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-Jump-Box Gateway and all dependencies
**10.0.0.5**
**10.0.0.6**
**10.0.0.7**

We have installed the following Beats on these machines:

Docker.io
Python3-pip

A variety of Filebeat and Metricbeat trackers. The User May specify any and all packages they wish to use.

@timestamp

_id

_index

_score

_type

agent.ephemeral_id

agent.hostname

agent.id

agent.type

agent.version

ecs.version

event.action

event.category

event.dataset

event.module

event.outcome

event.timezone

event.type

fileset.name

host.hostname

host.name

input.type

log.file.path

log.offset

message

process.name

process.pid

service.type

source.ip

suricata.eve.timestamp

system.auth.ssh.event

user.name


These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Filebeat_config.yml file to the $/etc/ansible.
- Update the config file to include... the ip address you want to have primary access for.
- Run the playbook, and navigate to Kibana server URL (specified address:port)/app/kibana to check that the installation worked as expected.

Run these commands to first change to the directory where the Elk.yml file will be saved (admins choice) You will run the following curl command to download the elk-server


