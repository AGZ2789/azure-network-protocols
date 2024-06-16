<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

![](https://i.imgur.com/waxVImv.png)

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


- [Simple List](https://docs.google.com/document/d/1jOKQFGxWc9hyJ6E6WSisWFqwyXvwe1YO7NCBKu7Rv54/edit)


<h2>Environments and Technologies Used</h2>


- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>


🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

<h2>Part 1 | Create our Resources</h2>

- Create a Resource Group
- Create a Windows 10 Virtual Machine (VM)
  - While creating the VM, select the previously created Resource Group
  - While creating the VM, allow it to create a new Virtual Network (Vnet) and Subnet
- Create a Linux (Ubuntu) VM
  - While create the VM, select the previously created Resource Group and Vnet
- Observe Your Virtual Network within Network Watcher

🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

![Snipaste_2024-06-15_14-36-48](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/66832a94-f90b-41cb-8273-1d87a0ca077a)

![Snipaste_2024-06-15_14-48-13](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/5265ddcf-61f0-457e-bb8b-74b00d3a812b)

![Snipaste_2024-06-15_14-51-32](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/ff2bdd03-9dd1-48ff-ba7d-c157571f079c)

![Snipaste_2024-06-15_15-00-16](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/c879a753-6a64-41d9-a354-abab5b2c043d)

![Snipaste_2024-06-15_15-16-03](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/cb2beeec-00c4-49ea-bb26-0704f55c07ae)

![Snipaste_2024-06-15_15-19-04](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/726453b7-6b6b-47fb-b99f-22b0018d3dd3)

![Snipaste_2024-06-15_15-20-56](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/e9d8522f-0cc4-4851-bf41-0786d4130f07)

![Snipaste_2024-06-15_16-49-36](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/aead9a77-874b-4198-aa43-19231075b2a7)

🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

<h2>Part 2 | Observe ICMP Traffic</h2>

- Use Remote Desktop to connect to your Windows 10 Virtual Machine
- Within your Windows 10 Virtual Machine (VM1)
  - Download & Install Wireshark
  - Open Wireshark and filter for ICMP traffic only
  - Retrieve the private IP address of the (Ubuntu VM2) and attempt to ping it from within the (Windows 10 VM1)
  - Observe ping requests and replies within WireShark
  - From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark

🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

![Snipaste_2024-06-15_17-03-08](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/91fc7937-6e46-4889-9c7f-575fd6e8af37)

![Snipaste_2024-06-15_17-07-33](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/3de00a63-ce9c-4807-80a4-be237af2fa6d)

![Snipaste_2024-06-15_20-18-07](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/70295070-2846-4a4b-b7cc-ec60cdd3e87f)

![Snipaste_2024-06-15_20-25-11](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/79cc7c7f-7735-4fb7-91f3-3093ea0b21f8)

![Snipaste_2024-06-15_20-28-21](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/39f87da9-93bb-460d-babb-71280590d07a)

![Snipaste_2024-06-15_20-30-21](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/6bedf44e-b157-4ca2-8e7c-5f716c7c8a21)

![Snipaste_2024-06-15_22-11-17](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/888ffd9e-a4f4-4e7f-9042-6611f7c421f3)

![Snipaste_2024-06-15_22-33-12](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/2da09b0c-cadf-48d6-932a-54af2e5b12a0)

🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

<h2>Part 3 | Observe SSH Traffic</h2>

- Back in Wireshark, filter for SSH traffic only
- From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
  - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
  - Exit the SSH connection by typing ‘exit’ and pressing [Enter]

🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

![Snipaste_2024-06-15_23-10-06](https://github.com/AGZ2789/azure-network-protocols/assets/84995125/64ce1bce-5a25-4c58-9bb4-e3ba45bebb80)

🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻🔻

<h2>Lab Cleanup (DON’T FORGET THIS)</h2>

- Close your Remote Desktop connection
- Delete the Resource Group(s) created at the beginning of this lab
- Verify Resource Group Deletion
