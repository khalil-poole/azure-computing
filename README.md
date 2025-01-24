# Monitoring Network Traffic with Azure

![image](https://github.com/user-attachments/assets/63276b6a-6580-455a-93fd-1d1a624d4a1f)

By setting up two Virtual Machines, we can analyze traffic going in and out to ensure network operations are smooth.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10
- Ubuntu Server 24.04

# Initial Setup

1. Login to your Microsoft Azure account, and create a Resource Group by typing in "resource group" in the search bar.

![image](https://github.com/user-attachments/assets/7dbda0a1-98ad-437c-857e-fdd8fb5f114d)


2. Click the "Create" button.

![image](https://github.com/user-attachments/assets/56020569-694e-49d3-9763-68b5be5a8e93)

3. Name the Resource Group, Select the Region of your choice, and then click on the "Review + Create" Tab to create the Resource Group.

![image](https://github.com/user-attachments/assets/a5e0ba05-785a-43e7-b6fe-014b998ab306)

![image](https://github.com/user-attachments/assets/d3393fdb-312a-415a-a273-96373dc0f74d)

4. Create two Virtual Machines, one with the Windows OS, and the second one with the Linux OS. We'll start by typing in "virtual machine" in the search bar.

![image](https://github.com/user-attachments/assets/efa4bf3e-cf04-4a9b-8cf0-57298b234f5a)

5. Click the "Create" button.

![image](https://github.com/user-attachments/assets/24060845-122c-4a60-a265-0fcd810b4e23)

6. Use the previously created Resource Group for the Virtual Machine to utilize. Name the VM (Virtual Machine for short), and keep the region the same as the one that the created Resource Group is using. Everything inside the red rectangles are changes that are required for this activity to work.

![image](https://github.com/user-attachments/assets/ef00c145-4db0-4d40-9e9c-5a626a7c1f53)

7. This is for the **WINDOWS VM ONLY** . Set the Image to Windows 10 Pro, and the size to atleast 8 GiB of memory.

![image](https://github.com/user-attachments/assets/85688e2b-c4ad-45e7-9ada-12d9f862259d)

8. Create a username and password, followed by clicking on the checkbox regarding the licensing agreement. Afterwards, we'll skip the Disks tab, and go to the Networking tab.

![image](https://github.com/user-attachments/assets/d5b7f243-a9c0-4695-bf72-d8c596a45a4e)

9. In the Networking Tab, we'll create a new Virtual Network (Vnet) for the Windows VM to use. By clicking on "Create new" under the "Virtual network" section, a new window will pop up. Rename the the Vnet, in the case of the screenshot, I renamed it to "Lab2-Vnet" and then click ok. Once completed, click "Review + Create", and then click "Create" once validation is passed. Validation is used to ensure that all settings are ready to be deployed by Azure. Creation of the VM may take a few minutes.

![image](https://github.com/user-attachments/assets/2658ad3a-2616-4980-b4ed-efebfc3e2301)

![image](https://github.com/user-attachments/assets/6ad1edc9-0572-464c-9de3-3e0986fd6846)


10. It's time to create the Linux OS. We'll start by repeating Steps 4 thru 6.

11. Create a unique name for the second VM, and this time we'll be choosing "Ubuntu 22.04 LTS -x64 Gen2" as our Image. This is for the **LINUX VM ONLY**.

![image](https://github.com/user-attachments/assets/a3b30a93-55a7-455b-9fd7-2ccc659e93fb)

12. We'll change the Authentication type to "Password", and from there create a username and password combination or use the previous credentials that were created for the Windows VM. Afterwards, we'll click "Review + Create" and then click "Create" like before.

![image](https://github.com/user-attachments/assets/11753046-3355-4282-b724-39827001922c)

# Observing ICMP Traffic

1. Login to the Remote Desktop with the Windows OS by using the VM's public IP Address and the login credentials created for the VM. The IP Address can be found by going to the VM itself. (For Mac users, please install Microsoft Remote Desktop)
2. 
