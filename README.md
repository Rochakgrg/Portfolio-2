# Portfolio 2 building a sandbox network
# Aims
A sandboxed network provides an essential learning environment and platform, offering a secure, isolated space to simulate real-world network scenarios without introducing risks to live systems. For this Portfolio, you will create your own private sandboxed virtual network using VirtualBox. The network will consist of multiple virtual machines (VMs) configured within a private IP address range. The aim is to gain an applied understanding of networking concepts, IP subnetting, network interface configuration, and a basic server setup, design, planning and organisation strategies.
# Task
You will create a small network that includes three virtual machine assets that will be networked. They are as follows:

Desktop VM: Used as the management interface for configuring other VMs, on subnet one.

Gateway VM: Acts as the network gateway with three LAN cards. One LAN card with internet access and another two LAN cards denoting two separate subnets.

Application Server VM: Can be any server of choice (e.g., web server, database server), on subnet two.
You can select a prebuilt server from Bitnami if you prefer.
# Devices Used:
1. Ubuntu 24 Desktop: https://ubuntu.com/desktop
2. Ubuntu Server as Gateway Router: https://moodle.roehampton.ac.uk/pluginfile.php/4873277/mod_resource/content/4/Setting%20Up%20a%20Ubuntu%20Gateway%20Router_v02.pdf
3. Bitnami Wordpress: https://bitnami.com/stacks/virtual-machine
# method: 
# Setting ip address in Ubuntu 24 Desktop:
1. Open Network settings and select IPV4 tab and input the ip address provided:
![4](https://github.com/user-attachments/assets/14988e1e-96b3-47f2-9912-58832c01406d)




  <img width="639" alt="Screenshot 2024-12-20 115222" src="https://github.com/user-attachments/assets/c539fac6-0909-4106-ac9c-32b0b8896c3c" />


2. Then try pinging the Bitnami and Gateway Router see if its reachable:
   

![3](https://github.com/user-attachments/assets/045f1371-047f-4543-9c1c-1b13cd8b14f3)



# Setting ip address in Bitnami Wordpress: 
1. Edit the network interfaces file with the command "sudo nano /etc/network/interfaces", and this file looks like the image below:

   
<img width="650" alt="bitnami_ip_address_setting" src="https://github.com/user-attachments/assets/b81bef2f-748f-4b00-9e39-13e6247fce72">

2. After editing and saving the file, try to ping Ubuntu24 desktop, and Gateway Router:

<img width="600" alt="bitnami_ping" src="https://github.com/user-attachments/assets/22ee2290-9f22-491c-80df-8613095c6a59">

# Setting ip address in Gateway Router: 
1. Edit the network interfaces file with the command "sudo nano /etc/netplan/50-cloud-init.yaml", and this file looks like the image below:

![E50B75A5-C5AE-4603-AC1B-AEEB3F5FA997_4_5005_c](https://github.com/user-attachments/assets/9583bfb7-f553-4f22-b73f-81b11a3410ca)


2. After editing and saving the file, try to ping Ubuntu24 desktop, and Bitnami:

<img width="600" alt="ubuntu_server_router_ping" src="https://github.com/user-attachments/assets/31bc7b1d-d72a-4112-96cd-30087e09b2fc">

# Conclusion:

After setting all 3 network devices, all three devices are pinging each other ip addresses successfully.
