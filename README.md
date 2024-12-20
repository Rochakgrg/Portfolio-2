# Portfolio 2 building a sandbox network
# Aims
This portfolio project involves building a safe, isolated virtual network using VirtualBox. This "sandbox" will consist of several virtual machines (VMs) operating within a private IP range. The goal is to gain hands-on experience with networking concepts like IP subnetting, configuring network interfaces, setting up a basic server, and applying design, planning, and organizational strategies.
# Task
This project requires setting up a network with three interconnected virtual machines (VMs):

Desktop VM: This VM will be used to manage and configure the other VMs and will reside on the first subnet.

Gateway VM: This VM will function as the network's gateway, equipped with three network interface cards (NICs). One NIC will provide internet access, while the other two will connect to two distinct subnets.

Application Server VM: Can be any server of choice (e.g., web server, database server), on subnet two.
You can select a prebuilt server from Bitnami if you prefer.
# Devices Used:
1. Ubuntu 24 Desktop: https://ubuntu.com/desktop
2. Ubuntu Server as Gateway Router: https://moodle.roehampton.ac.uk/pluginfile.php/4873277/mod_resource/content/4/Setting%20Up%20a%20Ubuntu%20Gateway%20Router_v02.pdf
3. Bitnami Wordpress: https://bitnami.com/stacks/virtual-machine
# method: 

 # Router: Ubuntu Server

Network Configuration:

On the router VM (Ubuntu Server), the primary network configuration file is /etc/netplan/50-cloud-init.yaml. This file contains the network settings for all adapters.

Command: sudo nano /etc/netplan/50-cloud-init.yaml

![05A1AA4F-9BCA-480C-9379-4B4C7E3231EA](https://github.com/user-attachments/assets/3c709e1f-42ea-4644-a495-f7452cad3290)

IP address of all adapters:
You may use the following command to confirm the IP addresses given to each network interface on the router after establishing the network settings:

Command: ip a

This command displays all ip address associated with the routers network interface

<img width="1372" alt="Screenshot 2024-12-20 at 12 54 09 PM" src="https://github.com/user-attachments/assets/f7f191b7-811d-4e6a-bf33-b0824af6855a" />

Pinging Desktop VM and Application VM:

Command to ping Desktop VM: ping 192.168.114.1

![0C7A34DE-C3ED-4AC2-9670-D7C13E3B0501_4_5005_c](https://github.com/user-attachments/assets/1dd204ae-f171-48b9-a921-df611b95e7e5)


Command to ping Application Server: ping 192.168.14.1

<img width="509" alt="Screenshot 2024-12-20 at 1 08 25 PM" src="https://github.com/user-attachments/assets/d5e483bd-711a-47ea-86cb-3a55e7c3b9fc" />

# Setting ip address in Ubuntu 24 Desktop:
1. Open Network settings and select IPV4 tab and input the ip address provided:

<img width="639" alt="Screenshot 2024-12-20 115113" src="https://github.com/user-attachments/assets/08799fda-edc2-4579-b641-d90053b4a51f" />



  <img width="639" alt="Screenshot 2024-12-20 115222" src="https://github.com/user-attachments/assets/c539fac6-0909-4106-ac9c-32b0b8896c3c" />

  Pinging to router:

To check if the Desktop VM can communicate with the router, ping the router's IP address (e.g., 10.0.2.15).

Command: ping 10.0.2.15

![71EE607D-AF05-40CE-A353-D1EF76B70591_4_5005_c](https://github.com/user-attachments/assets/404e5c26-01b0-4d98-936e-66a869d1dd0d)



2. Then try pinging the Bitnami and Gateway Router see if its reachable:
   

![3](https://github.com/user-attachments/assets/045f1371-047f-4543-9c1c-1b13cd8b14f3)



# Setting ip address in Bitnami Wordpress: 
1. Edit the network interfaces file with the command "sudo nano /etc/network/interfaces", and this file looks like the image below:

   Command: sudo nano /etc/network/interfaces
   
![4](https://github.com/user-attachments/assets/1b786c0d-0db1-4025-9666-ded5ede561bf)


3. After editing and saving the file, try to ping Ubuntu24 desktop, and Gateway Router:

<img width="1372" alt="Screenshot 2024-12-20 at 12 54 15 PM" src="https://github.com/user-attachments/assets/e9c7a063-70da-4769-ba2d-c825c5953b3d" />


# Setting ip address in Gateway Router: 
1. Edit the network interfaces file with the command "sudo nano /etc/netplan/50-cloud-init.yaml", and this file looks like the image below:

![E50B75A5-C5AE-4603-AC1B-AEEB3F5FA997_4_5005_c](https://github.com/user-attachments/assets/9583bfb7-f553-4f22-b73f-81b11a3410ca)


2. After editing and saving the file, try to ping Ubuntu24 desktop, and Bitnami:

![2](https://github.com/user-attachments/assets/66a2367f-3830-47ab-b5e3-736bd32c1129)


# Conclusion:

After setting all 3 network devices, all three devices are pinging each other ip addresses successfully.Success in the making of a functional, isolated virtual network through virtual box, which includes a Desktop VM to manage, a Gateway VM acting as router and with three network interfaces and an Application Server VM running Bitnami WordPress. The main focus was to provide hands-on experience with basic networking concepts like IP subnetting, configuring network interfaces, and setting up a simple server. networking principles.A functional Network Infrastructure was achieved by assigning Private IP addresses from different subnets and altering the network configuration files in each VM. Using the ping test between the VMs, I tested for network connectivity, which showed that network communication between the VMs was successful.

The project successfully showcased my skill to plan, design, and implement a basic network topology while gaining valuable hands-on experience with fundamental networking principles.Gateway VM is configured successfully as a router connecting two subnets and the internet, indicating a good knowledge of routing. Deploying Bitnami WordPress server further made these concepts practical. Once this is working the project provides a good basis to explore other networking concepts like firewalls and routing protocols or adding more services and VMS.

