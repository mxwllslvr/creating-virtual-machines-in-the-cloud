![Github Banner 1 - Creating VMs](https://github.com/user-attachments/assets/06bc162a-3c8c-442b-8cc9-87d963ba377d)

<h1>Creating a Windows and Linux Virtual Machine in the Cloud (Microsoft Azure)</h1>
In this walkthrough, we will create a Windows and Linux virtual machine (VM) in Azure. This skill set will be vital and is a key component to all of the IT projects listed. <br/>

<h2>🚨Prerequisites🚨</h2>

- <a href="https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account/search?ef_id=_k_Cj0KCQjwzYLABhD4ARIsALySuCTvMpKHbOeSo9lv81A8vCg1XGDNwpOIuOsD2o8pmLnyl7dVku-Yn3IaApK-EALw_wcB_k_&OCID=AIDcmmfq865whp_SEM__k_Cj0KCQjwzYLABhD4ARIsALySuCTvMpKHbOeSo9lv81A8vCg1XGDNwpOIuOsD2o8pmLnyl7dVku-Yn3IaApK-EALw_wcB_k_&gad_source=1&gbraid=0AAAAADcJh_uVoYZIZMJRJFQ3v8k-BGmp2&gclid=Cj0KCQjwzYLABhD4ARIsALySuCTvMpKHbOeSo9lv81A8vCg1XGDNwpOIuOsD2o8pmLnyl7dVku-Yn3IaApK-EALw_wcB)">An active Microsoft Azure account</a> 

<h2>Technologies Utilized</h2>

- Microsoft Azure (Compute/Virtual Machines)

<h2>Operating Systems</h2>

- macOS Sequoia
- Windows 10 Pro (22H2)
- Ubuntu Server 22.04 LTS

<h2>Procedure Overview</h2>

- Step 1: Establish a resource group in Azure
- Step 2: Provision a Windows VM
- Step 3: Provision a Linux VM

<h2>Detailed Instructions</h2>

<h3> Step 1: Establishing a resource group in Azure. </h3>

<p>
- Access the Azure Portal: Upon signing into your Azure account, you will be directed to the Azure Portal’s Quickstart Center.
</p>
<br/>

<p>
<img width="750" alt="CVM RG2" src="https://github.com/user-attachments/assets/856076ee-bfde-474d-b5ec-5ad7a2f300ab"/>
</p>
<p>
- Locate Resource Groups: Utilize the search bar at the top of the portal. Enter “resource” and select Resource Groups from the suggested options.
</p>

<br />


<p>
<img width="750" alt="CVM RG3" src="https://github.com/user-attachments/assets/358a46b1-bdc8-48d7-898f-1a592f724b7b"/>
</p>
<p> - Initiate Resource Group Creation: If no resource groups are listed, select the + Create button.</p>
<br />
<br />

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
<br />


<p>
<img width="750" alt="CVM RG5" src="https://github.com/user-attachments/assets/4aaa38db-926d-4470-acd0-ba921397c158" />
</p>
<p>
Finalize Creation: Confirm the Resource Group details, including name and region, and select Create. Upon completion, you will be redirected to the Resource Groups section, where the new group will be visible.
</p>
<br />

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


