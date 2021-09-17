{\rtf1\ansi\ansicpg1252\cocoartf1504\cocoasubrtf830
{\fonttbl\f0\fswiss\fcharset0 Helvetica;\f1\fnil\fcharset0 Monaco;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue255;\red255\green255\blue255;\red22\green21\blue22;
\red0\green0\blue192;\red152\green0\blue15;\red7\green64\blue153;\red16\green120\blue67;\red152\green66\blue3;
}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c100000;\cssrgb\c100000\c100000\c100000;\cssrgb\c11373\c10980\c11373;
\cssrgb\c0\c0\c80000;\cssrgb\c66667\c6667\c6667;\cssrgb\c0\c33333\c66667;\cssrgb\c0\c53333\c33333;\cssrgb\c66667\c33333\c0;
}
\margl1440\margr1440\vieww11540\viewh12940\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 \
\
\pard\pardeftab720\sl340\partightenfactor0

\f1\fs26 \cf2 \cb3 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 ## Automated ELK Stack Deployment\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 The files in this repository were used to configure the network depicted below.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 !\cf5 \ul \ulc5 \strokec5 [TODO: Update the path with the name of your diagram]\cf6 \ulnone \strokec6 (Images/diagram_filename.png)\cf4 \cb1 \strokec4 \
\cb3 \uc0\u8203 \cb1 \
\cb3 These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3   \cf7 \strokec7 - /etc/ansible/elk.yml\cf4 \cb1 \strokec4 \
\cb3 \uc0\u8203 \cb1 \
\cb3 This document contains the following details:\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - Description of the Topologu\cf4 \cb1 \strokec4 \
\cf7 \cb3 \strokec7 - Access Policies\cf4 \cb1 \strokec4 \
\cf7 \cb3 \strokec7 - ELK Configuration\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3   \cf8 \strokec8 - Beats in Use\cf4 \cb1 \strokec4 \
\cb3   \cf8 \strokec8 - Machines Being Monitored\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - How to Use the Ansible Build\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 \uc0\u8203 \cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf2 \cb3 \strokec2 ### Description of the Topology\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 Load balancing ensures that the application will be highly secure, in addition to restricting access to the network.\cb1 \
\cb3 	What aspect of security do load balancers protect?\cb1 \
\cb3   	Load balancers evenly distribute HTTP traffic to the servers, preventing server attacks such as DDoS attacks\cb1 \
\cb3         What is the advantage of a jump box?\cb1 \
\cb3         Jump boxes provide secure connection to the server\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.\cb1 \
\cb3 	What does Filebeat watch for?\cb1 \
\cb3 	Filebeat watches for changes by collecting and logging files and events; forwarding them to Kibana for analysis. \cb1 \
\cb3 	What does Metricbeat record?\cb1 \
\cb3 	Metricbeat is installed on a host to monitor and record performance metrics.\cb1 \
\cb3 The configuration details of each machine may be found below.\cb1 \
\cb3 _Note: Use the \cf5 \ul \ulc5 \strokec5 [Markdown Table Generator]\cf6 \ulnone \strokec6 (http://www.tablesgenerator.com/markdown_tables)\cf4 \strokec4  to add/remove values from the table_.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 | Name          | Function    | IP Address  | Operating System |\cb1 \
\cb3 |\'97-\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97|\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97-|\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97|\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97\'97-\'97|\cb1 \
\cb3 | Jump Box      | Gateway     | 10.1.0.4    | Linux            |\cb1 \
\cb3 | Web1-DVWA     | Webserver   | 10.0.0.7    | Linux            |\cb1 \
\cb3 | Web2-DVWA     | Webserver   | 10.0.0.8    | Linux            |\cb1 \
\cb3 | ELK-Server    |ELK Server   | 10.2.0.5    | Linux            |\cb1 \
\cb3 | Load Balancer |Load Balancer| 52.186.149.216| Linux          |\cb1 \
\cb3 \uc0\u8203 \cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf2 \cb3 \strokec2 ### Access Policies\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 The machines on the internal network are not exposed to the public Internet. \cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 Only the ELK Server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:\cb1 \
\cb3 Workstation 13.89.51.194 through TCP on port 5601.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 Machines within the network can only be accessed by workstation and the jumpbox.\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - Which machine did you allow to access your ELK VM? What was its IP address?\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3   \cf7 \strokec7 I used Jump-Box-Provisioner IP 20.102.84.195 SSH port 22 to access my ELK VM and its IP address is 13.89.51.194 \cf4 \cb1 \strokec4 \
\cb3 \uc0\u8203 \cb1 \
\cb3 A summary of the access policies in place can be found in the table below.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 | Name         | Publicly Accessible | Allowed IP Addresses |\cb1 \
\cb3 |--------------|---------------------|----------------------|\cb1 \
\cb3 | Jump Box     | No                  | 52.186.149.216       |\cb1 \
\cb3 | Web1-DVWA    | No                  | 10.0.0.7             |\cb1 \
\cb3 | Web2-DVWA    | No                  | 10.0.0.8             |\cb1 \
\cb3 | ELK Server   | No                  | 40.83.40.50          |\cb1 \
\cb3 | Load Balancer| No                  | 52.142.57.13         |\cb1 \
\cb3 \uc0\u8203 \cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf2 \cb3 \strokec2 ### Elk Configuration\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - What is the main advantage of automating configuration with Ansible?\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3   \cf7 \strokec7 Ansible will quickly make changes to the system, rather than doing each one manually.\cf4 \cb1 \strokec4 \
\cb3 \uc0\u8203 \cb1 \
\cb3 The playbook implements the following tasks:\cb1 \
\cb3 In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.\cb1 \
\cb3 ... Install docker.io\cb1 \
\cb3 ... Install pip3\cb1 \
\cb3 ... Install Docker python module\cb1 \
\cb3 ... Increase virtual memory\cb1 \
\cb3 ... Download and Launch Docker\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 The following screenshot displays the result of running \cf9 \strokec9 `docker ps`\cf4 \strokec4  after successfully configuring the ELK instance.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 !\cf5 \ul \ulc5 \strokec5 [TODO: Update the path with the name of your screenshot of docker ps output]\cf6 \ulnone \strokec6 (Images/docker_ps_output.png)\cf4 \cb1 \strokec4 \
\cb3 \uc0\u8203 \cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf2 \cb3 \strokec2 ### Target Machines & Beats\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 This ELK server is configured to monitor the following machines:\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - List the IP addresses of the machines the Elk_Server is configured to monitor:\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 	\cf7 \strokec7 Web1-DVWA: 10.0.0.7\cf4 \cb1 \strokec4 \
\cb3 	\cf7 \strokec7 Web2-DVWA: 10.0.0.8\cf4 \cb1 \strokec4 \
\cb3 We have installed the following Beats on these machines:\cb1 \
\cb3 	FileBeats\cb1 \
\cb3 	MetricBeats\cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 These Beats allow us to collect the following information from each machine:\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., \cf9 \strokec9 `Winlogbeat`\cf7 \strokec7  collects Windows logs, which we use to track user logon events, etc.\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 FileBeats are used as a lightweight shipper for forwarding and centralizing log data. The data FileBeat collects is about changes in the filesystem. An example of a FileBeat are Apache Access Logs that can be used for monitoring traffic to your service. \cb1 \
\cb3 MetricBeats collect machine metrics, such as uptime. They are installed on different servers in my environment and are used for monitoring performance.\cb1 \
\cb3 \uc0\u8203 \cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf2 \cb3 \strokec2 ### Using the Playbook\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: \cb1 \
\cb3 \uc0\u8203 \cb1 \
\cb3 SSH into the control node and follow the steps below:\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - Copy the filebeat-config.yml and filebeat-playbook.yml file to the /etc/Ansible/ directory.\cf4 \cb1 \strokec4 \
\cf7 \cb3 \strokec7 - Update the hosts file to include the host IP address in filebeat-config.yml file.\cf4 \cb1 \strokec4 \
\cf7 \cb3 \strokec7 - Run the playbook, and navigate to Kibana to check that the installation worked as expected.\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 Answer the following questions to fill in the blanks:_\cb1 \
\pard\pardeftab720\sl340\partightenfactor0
\cf7 \cb3 \strokec7 - _Which file is the playbook? Where do you copy it? elk.yml and it is located inside /etc/ansible/elk.yml\cf4 \cb1 \strokec4 \
\cf7 \cb3 \strokec7 - _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?  \cf4 \cb1 \strokec4 \
\cf7 \cb3 \strokec7 - _Which URL do you navigate to in order to check that the ELK server is running?\cf4 \cb1 \strokec4 \
\pard\pardeftab720\sl340\partightenfactor0
\cf4 \cb3 \uc0\u8203 \cb1 \
\cb3 _As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.\cb1 \
\cb3 cd /etc/ansible curl -i href="\cf5 \ul \ulc5 \strokec5 https://github.com/Jfschoellkopf/AzureLab.git\cf4 \ulnone \strokec4 " ansible-playbook /etc/ansible/elk.yml\cb1 \
}