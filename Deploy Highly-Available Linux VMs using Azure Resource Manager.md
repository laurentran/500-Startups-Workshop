# Microsoft Azure: 500 Startups Workshop
## Hands-on Lab 2
## Deploy Highly-Available Linux VMs using Azure Resource Manager


[Azure Resource Manager (ARM)](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview) allows you to quickly and easily deploy Azure services through templates.  Using ARM templates, you can deploy, manage, and monitor your resources as a group.  They enable you to manage your infrastructure through declarative JSON templates, rather than scripts.  

To quickly deploy a highly-available set of Virtual Machines (VMs), follow the steps below.  

1.	Log into your Azure portal at [portal.azure.com](portal.azure.com) using the Microsoft Account email that you used to register for BizSpark.

2.	To create 2 Ubuntu VMs behind a load balancer using an ARM template, go to [Linux VMs Availability Set](https://github.com/mschray/AzureVMCreate).  This template configures your 2 VMs in an Availability Set, which is required for high-availability (no single point of failure).  

* For Windows VMs, see [Windows VMs Availability Set](https://github.com/Azure/azure-quickstart-templates/tree/master/201-2-vms-loadbalancer-lbrules).  Our lab follows the Linux template, but you can follow along using the Windows template.]  

3.	Click on “**Deploy to Azure**”.  This button deep links to the Azure portal and will open your Azure portal in a new window.  

* ![](/images/deploy-to-azure.jpg)

4.	You will see the following screen in your Azure Portal.  Under **Subscription**, choose **Microsoft Azure Sponsorship** (or the name of the subscription that is tied to your $360,000 Azure credits).  

* ![](/images/edit-arm-portal.png)

5.	Under **Resource Group**, create a new resource group.  This is a logical grouping for your services, so choose a name that makes sense for the logical container where your services will be grouped.  

6.	Under **Location**, choose the Azure region to deploy your services.

7.	Fill out the **Admin Username** (the username for the VMs) and **Admin Password** (password for the VMs).  You can later use these credentials to RDP or SSH into the VMs.  

8.	Enter a **DNS Name for LBIP**, a unique DNS name for the Public IP of your load balancer.  

9.	Enter names for **VM Name Prefix** (prefix for your VMs), **LB Name** (load balancer name), **NIC Name Prefix** (prefix for your NICs), **Public IP Address Name**, and **VNET Name** (virtual network name).

10.	Under **Image SKU**, choose the Ubuntu version for your VMs.  

11.	Under **VM Size**, choose **Standard_D2_v2** for a general-purpose VM with 2 cores and 7 GBs memory.  See [Linux VM Sizes](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/sizes) or [Windows VM Sizes](https://docs.microsoft.com/en-us/azure/virtual-machines/virtual-machines-windows-sizes) for a complete list of VM sizes.  

12.	[OPTIONAL]: To view the ARM template JSON file and to edit it from the Azure Portal, click on “Edit template”.  
 
* On the left pane, you’ll see your **Parameters** (we filled these out in steps 7-11), **Variables**, and **Resources**.  Click on any of these items to quickly locate them in the editor on the right.  

* ![](/images/arm-editor.png)

* Click **Save** or **Discard** to go back.

13.	Once you’ve completed the fields and agreed to the Terms and Conditions, click the **Purchase** button to deploy.  When the deployment is complete, your resources will show up on your dashboard under **All Resources**.  

You can find additional pre-built ARM templates on [GitHub: Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) or in the [Azure Quickstart Templates](https://azure.microsoft.com/en-us/resources/templates/) gallery for your scenario.  
