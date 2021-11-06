
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- I whitelisted my personal IP address

Machines within the network can only be accessed by SSH.
-Which machine did you allow to access your ELK VM? What was its IP address? Jumpbox 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |     10.0.0.4         |
|  ELK     | no                  |     10.1.0.4         |
|  Web     | no                  |     10.0.0.5-6       |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-What is the main advantage of automating configuration with Ansible? You can configure multiple machines at once

The playbook implements the following tasks:
-In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Docker; Install pip3; Install Docker python; Increase virtual memory; Download and launch docker elk container


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(/Images/dockerpsoutput.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- List the IP addresses of the machines you are monitoring 10.0.0.5; 10.0.0.6

We have installed the following Beats on these machines:
-Specify which Beats you successfully installed Metricbeat filebeat

These Beats allow us to collect the following information from each machine:
-In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Metricbeat collects machine metrics, like uptime. Filebeat collects data about	the file system.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the public key file to ansible.
- Update the config file to include correct IP adresses
- Run the playbook, and navigate to kibana to check that the installation worked as expected.


- _Which file is the playbook? Where do you copy it? the playbook is a yml file and it needs to be copied to the applications' folder
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? ELK conifig file is run on the elk stack server, then the filebeat install is run on the container level.
- _Which URL do you navigate to in order to check that the ELK server is running? http:vmIP:5601/app/kibana
