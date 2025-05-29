<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

![Github Banner 1 - Creating VMs](https://github.com/user-attachments/assets/06bc162a-3c8c-442b-8cc9-87d963ba377d)

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

# Deploying Windows and Linux Virtual Machines in Microsoft Azure

This guide provides a structured procedure for provisioning Windows and Linux virtual machines (VMs) within Microsoft Azure. Mastery of this process is essential for professionals managing cloud-based IT infrastructure.

## 🚨 Prerequisites

- [An active Microsoft Azure account](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account/)

## Technologies Utilized

- Microsoft Azure (Compute/Virtual Machines)

## Operating Systems

- Windows 11 Home (24H2)
- Windows 10 Pro (22H2)
- Ubuntu Server 22.04 LTS

## Procedure Overview

1. Establish a resource group in Azure
2. Provision a Windows VM
3. Provision a Linux VM

---

## Step 1: Establish a Resource Group in Azure

### Access the Azure Portal
Upon signing into your Azure account, you will be directed to the Azure Portal's Quickstart Center.

### Locate Resource Groups
Utilize the search bar at the top of the portal. Enter "resource" and select **Resource Groups** from the suggested options.

![Azure Portal](https://github.com/user-attachments/assets/856076ee-bfde-474d-b5ec-5ad7a2f300ab)

### Initiate Resource Group Creation
If no resource groups are listed, select the **+ Create** button.

![Resource Groups Search](https://github.com/user-attachments/assets/358a46b1-bdc8-48d7-898f-1a592f724b7b)

### Configure Resource Group Settings

![Create Resource Group](https://github.com/user-attachments/assets/208466a1-6197-4212-a517-52465369b034)

![Resource Group Configuration](https://github.com/user-attachments/assets/4aaa38db-926d-4470-acd0-ba921397c158)

- **Subscription**: Verify that the appropriate subscription is selected from the dropdown menu
- **Name**: Assign a descriptive name to the Resource Group (e.g., "CloudInfraRG"). This will serve as the container for your VMs
- **Region**: Select **(US) East US 2**. Consistency in region selection across resources is critical to prevent configuration conflicts

Proceed by pressing **Next** until you reach the **Review + Create** section.

### Finalize Creation
Confirm the Resource Group details, including name and region, and select **Create**. Upon completion, you will be redirected to the Resource Groups section, where the new group will be visible.

---

## Step 2: Provision a Windows VM

### Navigate to Virtual Machines
In the Azure Portal, use the search bar to enter "virtual" and select **Virtual Machines** from the results.

![Virtual Machines Search](https://github.com/user-attachments/assets/ad54db79-1e24-464e-ba0d-368025a38f60)

### Begin VM Creation
Select the **+ Create** button to initiate the process.

![Create VM](https://github.com/user-attachments/assets/2e868182-061c-43b3-b18b-cc22e28562d0)

### Specify VM Type
Choose **Azure virtual machine** from the dropdown and select **Create**.

![VM Type Selection](https://github.com/user-attachments/assets/2e804b31-bfbb-4097-8302-2593baa666f7)

### Configure Core Settings

![VM Core Settings](https://github.com/user-attachments/assets/cb6bd1b8-a9ac-4b75-a011-b3ddc4003875)

- **Subscription**: Ensure the correct subscription is selected
- **Resource Group**: Choose the Resource Group created earlier (e.g., "CloudInfraRG")
- **VM Name**: Enter "windows-vm"
- **Region**: Select **(US) East US 2** to align with the Resource Group
- **Image**: Select **Windows 10 Pro, version 22H2** as the operating system (avoid selecting Windows Server images)

### Select VM Size

![VM Size Selection](https://github.com/user-attachments/assets/0508247f-af54-4652-8298-5718952d2d57)

In the **Size** field, choose **Standard_D2s_v3 - 2 vCPUs, 8 GiB memory**. If unavailable, select **See all sizes** and choose an equivalent with at least 2 vCPUs and 8 GiB memory.

### Define Administrative Credentials

![Admin Credentials](https://github.com/user-attachments/assets/8cfe7e8b-744b-41c3-89a0-0e9534f4a544)

- Create a username and password for the VM. Store these credentials securely, as they are required for Remote Desktop Protocol (RDP) access
- Under **Licensing**, check the box to confirm eligibility for Windows 10. This is mandatory for successful deployment

### Configure Disks
Select **Next: Disks** and retain the default disk configurations.

![Disk Configuration](https://github.com/user-attachments/assets/c776ad1d-35e1-4c38-98cf-b8c1672583ab)

### Configure Networking

![Network Configuration](https://github.com/user-attachments/assets/e69530ff-77f0-41c4-89e3-24baff76dea9)

- Create a new Virtual Network (e.g., "cloud-vnet"). Record this name for future reference
- Retain default settings for Subnet, Public IP, and the RDP port (3389) to enable remote access
- Continue **Next** until you reach the **Review + Create** page

### Validate and Deploy

![Validation](https://github.com/user-attachments/assets/ee8183e8-e341-42e2-8cb5-559a689e0074)

Verify the configuration, including subscription, Resource Group, region, VM name, image, size, and RDP settings. Select **Create**.

### Monitor Deployment

![Deployment Complete](https://github.com/user-attachments/assets/752f420e-a429-4839-ab57-3dd806c6724e)

Deployment may take several minutes. Upon completion, the message "Your deployment is complete" will appear. Select **Create another VM** to proceed with the Linux VM.

---

## Step 3: Provision a Linux VM

### Initiate Linux VM Setup

![Linux VM Setup](https://github.com/user-attachments/assets/5184be73-53a7-4704-a956-79d8e07ebda0)

From the VM creation screen, configure the following:
- **Resource Group**: Select the same Resource Group (e.g., "CloudInfraRG")
- **Name**: Enter "linux-vm"
- **Region**: Set to **(US) East US 2** for consistency
- **Image**: Choose **Ubuntu Server 22.04 LTS**

### Specify Size and Authentication

![Linux VM Configuration](https://github.com/user-attachments/assets/c39e1649-0021-46e1-bccc-c2cd5ff698df)

- **Size**: Select **Standard_D2s_v5 - 2 vCPUs, 8 GiB memory**, consistent with the Windows VM
- **Authentication type**: Set to **Password** (default is SSH public key)
- **Credentials**: Provide a username and password. For simplicity, you may reuse the Windows VM credentials. Store these securely

Select **Next** to proceed to disks and maintain the default settings. Proceed again by pressing **Next** to networking.

### Configure Networking

![Linux Network Configuration](https://github.com/user-attachments/assets/2a1b8070-259d-4647-9df6-4db8ce8481ea)

- **Virtual Network**: Choose the Virtual Network created for the Windows VM (e.g., "cloud-vnet")
- Retain default settings for Subnet and Public IP
- Continue **Next** until you reach the **Review + Create** page

### Validate and Deploy

![Linux VM Validation](https://github.com/user-attachments/assets/47e4d738-3616-432b-97f9-39b506b0bd77)

Confirm the settings, including Resource Group, region, VM name, image, size, and network configuration. Select **Create**.

### Monitor Deployment and Review VMs

![VM Overview](https://github.com/user-attachments/assets/97a2f2a8-d4a2-4e87-8185-82eddc4aa654)

Deployment will take several minutes. Upon completion, the message "Your deployment is complete" will appear.

Use the search bar to return to **Virtual Machines**. Both "Windows-VM" and "Linux-VM" will be listed, displaying details such as resource group, region, operating system, and public IP addresses.

**Note**: The Start, Stop, and Restart options in the Virtual Machines section allow you to manage VM states. To optimize costs, stop VMs when not in use. For additional practice, you may delete the Resource Group and repeat the process.

---

<br/><br/>

<div align="center"> <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExazdxOXFrZDl6YmUwdGgxamhpYzRuNWFpbnV5bWRyc2lsYXlsZHNzMiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/l1AsI389lnxkvQHAc/giphy.gif" width="100%"> </div>

<br/><br/>

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

## Conclusion

This procedure successfully establishes a Resource Group, a Windows VM running Windows 10 Pro, and a Linux VM running Ubuntu Server 22.04 LTS in Microsoft Azure. These virtualized environments provide scalable, cost-efficient resources for IT operations, eliminating the need for physical hardware. 

Enterprises leverage such cloud solutions for their flexibility and economic benefits. Ensure VMs are stopped when idle to manage subscription costs.

**Key takeaways:**
- Both VMs are deployed in the same region and virtual network for optimal connectivity
- Authentication credentials are required for accessing both Windows (RDP) and Linux (SSH) VMs
- Resource management is critical for cost optimization in cloud environments

This concludes the deployment process.

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

<br/><br/>

<div align="center">

<a href="HTTP://www.github.com/mxwllslvr">- BACK TO MAIN PAGE -</a>

</div>
