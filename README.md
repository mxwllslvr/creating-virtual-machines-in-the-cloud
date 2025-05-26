<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

![Github Banner 1 - Creating VMs](https://github.com/user-attachments/assets/06bc162a-3c8c-442b-8cc9-87d963ba377d)

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

<h1>Deploying Windows and Linux Virtual Machines in Microsoft Azure</h1>

This guide provides a structured procedure for provisioning a Windows and Linux virtual machine (VM) within Microsoft Azure. Mastery of this process is essential for professionals managing cloud-based IT infrastructure. <br/><br/>

<h2>🚨Prerequisites🚨</h2>
- <a href="https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account/search?ef_id=_k_Cj0KCQjwzYLABhD4ARIsALySuCTvMpKHbOeSo9lv81A8vCg1XGDNwpOIuOsD2o8pmLnyl7dVku-Yn3IaApK-EALw_wcB_k_&OCID=AIDcmmfq865whp_SEM__k_Cj0KCQjwzYLABhD4ARIsALySuCTvMpKHbOeSo9lv81A8vCg1XGDNwpOIuOsD2o8pmLnyl7dVku-Yn3IaApK-EALw_wcB_k_&gad_source=1&gbraid=0AAAAADcJh_uVoYZIZMJRJFQ3v8k-BGmp2&gclid=Cj0KCQjwzYLABhD4ARIsALySuCTvMpKHbOeSo9lv81A8vCg1XGDNwpOIuOsD2o8pmLnyl7dVku-Yn3IaApK-EALw_wcB)">An active Microsoft Azure account</a>
<br/><br/>
<h2>Technologies Utilized</h2>
- Microsoft Azure (Compute/Virtual Machines)
<br/><br/>
<h2>Operating Systems</h2>
- macOS Sequoia<br/>
- Windows 10 Pro (22H2)<br/>
- Ubuntu Server 22.04 LTS<br/>
<br/>
<h2>Procedure Overview</h2>
- Step 1: Establish a resource group in Azure<br/>
- Step 2: Provision a Windows VM<br/>
- Step 3: Provision a Linux VM<br/>
<br/><br/>

<h1>Detailed Instructions</h1>

<h2>Step 1: Establishing a resource group in Azure.</h2>

<p>
Access the Azure Portal: Upon signing into your Azure account, you will be directed to the Azure Portal’s Quickstart Center.
</p>

<p>
<img width="750" alt="CVM RG2" src="https://github.com/user-attachments/assets/856076ee-bfde-474d-b5ec-5ad7a2f300ab"/>
</p>

<p>
Locate Resource Groups: Utilize the search bar at the top of the portal. Enter “resource” and select Resource Groups from the suggested options.
</p>
<br/><br/>

<p>
<img width="750" alt="CVM RG3" src="https://github.com/user-attachments/assets/358a46b1-bdc8-48d7-898f-1a592f724b7b"/>
</p>
<p> - Initiate Resource Group Creation: If no resource groups are listed, select the + Create button.</p>
<br/><br/>
<p>
<img width="750" alt="CVM RG4" src="https://github.com/user-attachments/assets/208466a1-6197-4212-a517-52465369b034" />
</p>
<p> 
Configure Resource Group Settings:

Subscription: Verify that the appropriate subscription is selected from the dropdown menu.

Name: Assign a descriptive name to the Resource Group (e.g., “CloudInfraRG”). This will serve as the container for your VMs.

Region: Select (US) East US 2. Consistency in region selection across resources is critical to prevent configuration conflicts. 

Proceed by selecting Next, then Review + Create.
</p>
<br/>
<br/>
<p>
<img width="750" alt="CVM RG5" src="https://github.com/user-attachments/assets/4aaa38db-926d-4470-acd0-ba921397c158" />
</p>
<p>
Finalize Creation: Confirm the Resource Group details, including name and region, and select Create. Upon completion, you will be redirected to the Resource Groups section, where the new group will be visible.
</p>

<h3> Step 2: Provisioning a Windows Virtual Machine in Azure </h3><p>
<img width="750" alt="CVM 1" src="https://github.com/user-attachments/assets/ad54db79-1e24-464e-ba0d-368025a38f60"/>
</p>
<p>
Navigate to Virtual Machines: In the Azure Portal, use the search bar to enter “virtual” and select Virtual Machines from the results.
</p>
<br/>

<p>
<img width="750" alt="CVM 2" src="https://github.com/user-attachments/assets/2e868182-061c-43b3-b18b-cc22e28562d0"/>
</p>
Begin VM Creation: Select the + Create button to initiate the process.
</p>
<br />

<p>
<img width="750" alt="CVM 3" src="https://github.com/user-attachments/assets/2e804b31-bfbb-4097-8302-2593baa666f7" />
</p>
<p>
Specify VM Type: Choose Azure virtual machine from the dropdown and select Create.
</p>
<br />

<p>
<img width="750" alt="CVM 5" src="https://github.com/user-attachments/assets/cb6bd1b8-a9ac-4b75-a011-b3ddc4003875" />
</p>
<p>
Configure Core Settings:

Subscription: Ensure the correct subscription is selected.

Resource Group: Choose the Resource Group created earlier (e.g., “CloudInfraRG”).

VM Name: Enter “windows-vm”.

Region: Select (US) East US 2 to align with the Resource Group.

Image: Select Windows 10 Pro, version 22H2 as the operating system. Avoid selecting Windows Server images.
</p>
<br />

<p>
<img width="750" alt"CVM 6" src="https://github.com/user-attachments/assets/0508247f-af54-4652-8298-5718952d2d57"/>
</p>

<p>Select VM Size: In the Size field, choose Standard_D2s_v3 - 2 vCPUs, 8 GiB memory. If unavailable, select See all sizes and choose an equivalent with at least 2 vCPUs and 8 GiB memory.
</p>

<br/>


<p>
<img width="750" alt="CVM 7" src="https://github.com/user-attachments/assets/8cfe7e8b-744b-41c3-89a0-0e9534f4a544" />
</p>
<p>
 Define Administrative Credentials: Create a username and password for the VM. Store these credentials securely, as they are required for Remote Desktop Protocol (RDP) access.

Confirm Licensing: Under Licensing, check the box to confirm eligibility for Windows 10. This is mandatory for successful deployment.
</p>
<br />

<p>

<img width="750" alt="CVM 8" src="https://github.com/user-attachments/assets/c776ad1d-35e1-4c38-98cf-b8c1672583ab"/>
</p>
<p>
Advance to Disks: Select Next: Disks and retain the default disk configurations.
</p>
<br />

<p>
<img width="750" alt="CVM 9" src="https://github.com/user-attachments/assets/e69530ff-77f0-41c4-89e3-24baff76dea9"/>
</p>

<p>
Configure Networking:

In the Networking tab, create a new Virtual Network (e.g., “cloud-vnet”). Record this name for future reference.

Retain default settings for Subnet, Public IP, and the RDP port (3389) to enable remote access.

Continue next until you reach the "review + create" page.

</p>
<br/>

<p>
<img width="750" alt="CVM 10" src="https://github.com/user-attachments/assets/ee8183e8-e341-42e2-8cb5-559a689e0074"/>
</p>

<p>
Validate and Deploy: Verify the configuration, including subscription, Resource Group, region, VM name, image, size, and RDP settings. Select Create.
</p>

<br/>

<p>
<img width="750" alt="CVM 11" src="https://github.com/user-attachments/assets/752f420e-a429-4839-ab57-3dd806c6724e" />
</p>
<p>
Monitor Deployment: Deployment may take several minutes. Upon completion, the message “Your deployment is complete” will appear. Select Create another VM to proceed with the Linux VM.
</p>
<br />

<h3> Step 3: Create a Linux VM in Azure </h3>

<p>
<img width="750" alt="CVM 12" src="https://github.com/user-attachments/assets/5184be73-53a7-4704-a956-79d8e07ebda0"/>
</p>
<p>
Initiate Linux VM Setup: From the VM creation screen, select the same Resource Group (e.g., “CloudInfraRG”).

Define Name and Region:

Name the VM “linux-vm”.

Set the region to (US) East US 2 for consistency.

Select Operating System: Choose Ubuntu Server 22.04 LTS as the image.
</p>
<br/>

<p>
<img width="750" alt="CVM 14" src="https://github.com/user-attachments/assets/c39e1649-0021-46e1-bccc-c2cd5ff698df"/>
</p>
<p>Specify Size: Select Standard_D2s_v5 - 2 vCPUs, 8 GiB memory, consistent with the Windows VM.

Configure Authentication:

Set Authentication type to Password (default is SSH public key).

Provide a username and password. For simplicity, you may reuse the Windows VM credentials. Store these securely.

Select next to proceed to disks and maintain the default settings. Proceed again by pressing next to networking.
</p>
<br />

<p>
<img width="750" alt="CVM 15" src="https://github.com/user-attachments/assets/2a1b8070-259d-4647-9df6-4db8ce8481ea"/>
</p>
<p>
Configure Networking:

Choose the Virtual Network created for the Windows VM (e.g., “cloud-vnet”).

Retain default settings for Subnet and Public IP.

Continue next until you reach the "review + create" page.
</p>
<br />

<p>
<img width="750" alt="CVM 16" src="https://github.com/user-attachments/assets/47e4d738-3616-432b-97f9-39b506b0bd77"/>
</p>
<p>
Validate and Deploy: Confirm the settings, including Resource Group, region, VM name, image, size, and network configuration. Select Create.

Monitor Deployment: Deployment will take several minutes. Upon completion, the message “Your deployment is complete” will appear.
</p>

<p>
<img width="750" alt="CVM 18" src="https://github.com/user-attachments/assets/97a2f2a8-d4a2-4e87-8185-82eddc4aa654" />
</p>
<p>
Review VMs: Use the search bar to return to Virtual Machines. Both “windows-vm” and “linux-vm” will be listed, displaying details such as esource Group, region, operating system, and Public IP addresses.

Note: The Start, Stop, and Restart options in the Virtual Machines section allow you to manage VM states. To optimize costs, stop VMs when not in use. For additional practice, you may delete the Resource Group and repeat the process.  
</p>
<br />

<h2>✅ Conclusion</h2>

<p>
This procedure successfully establishes a Resource Group, a Windows VM running Windows 10 Pro, and a Linux VM running Ubuntu Server 22.04 LTS in Microsoft Azure. These virtualized environments provide scalable, cost-efficient resources for IT operations, eliminating the need for physical hardware. Enterprises leverage such cloud solutions for their flexibility and economic benefits. Ensure VMs are stopped when idle to manage subscription costs. This concludes the deployment process.
</p>
<br />
