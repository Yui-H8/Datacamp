# Understanding Microsoft Azure
---
**Description**

Start your journey towards Azure certification with this introductory course, designed to guide you through the fundamental building blocks of Microsoft Azure. Tailored for those preparing for Microsoft’s Azure Fundamentals Certification (AZ-900), you’ll explore key Azure services such as computing, storage, and databases while also learning to secure and optimize your cloud environment. By the end of this course, you will have a strong foundation in Azure’s ecosystem and be well on your way to mastering the essentials for certification and beyond.

### Navigating Azure's services
In this exercise, you'll login to the portal for the very first time and start familiarizing yourself with the Azure interface.

1. Step1   
Once logged in, you'll enter the Azure homepage which provides an overview of popular services as well as recently used resources, and quick start options.

**Note**: depending on your regional settings, your Azure Portal might be displayed in another language. To quickly change the language to English, click the gear icon at the top right, select the third tab on the left (about language and region), and then change the language appropriately.

2. Step2
   Navigate to the menu bar, and go to "All services".

3. Step3
   Under the "All services" section, you can explore all the tools that Azure has to offer including categories such as AI & Machine Learning, Compute, Storage and more.

Take some time to explore the various available categories and sub-categories.

4. Step4
   Within the "All services" menu on the left, find and navigate to the "Storage" category.

5. Which of the following does not fall under the sub-header of “Object, File and Block Storage”?

Answer: DataLake strage G1

### Benefits of cloud services
The cloud offers many benefits to its customers. Which of the following are general benefits of being on the cloud, and which of the following are key benefits of the Azure cloud?

*Congratulations! Azure has some extra key benefits when you're working with Microsoft, but the other main cloud providers also offer key benefits such as flexibility and scalability!*

### Choosing the right storage option
When working in the cloud having data storage that is resilient, highly available and protected against failure is important. You are creating your first Azure storage account and need to choose a redundancy option that meets the following criteria:

Supports backups through second region failover
Provides highly available access that's protected against data-center level issues
Which of the following storage type best suits our requirements?

*Great job! This option offers both GRS and ZRS which is recommended for critical data scenarios.*

---
### Identity and access management
Which of the following is Microsoft's cloud-based identity and access management service?
```
Azure Compute
〇 Microsoft Entra ID (formerly Azure Active Directory)
Azure Networking
Azure Storage
```
*Well done! Microsoft Entra ID (formerly Azure Active Directory) is Microsoft's identity and access management service.*

---
### Creating a virtual machine
Understanding how to create and configure VMs is crucial for deploying applications and services in the cloud. In this exercise, you'll be working on Azure to create your first virtual machine.

Note: To avoid any policy restriction errors, make sure your virtual machine follows all the exact requirements laid out in the exercise.
1. Step1
   * Navigate to the menu bar, and select "Virtual Machines"
2. Step2
   * To create a new virtual machine, select Create and choose "Azure virtual machine" from the dropdown
   * Set a custom name for your virtual machine under the subscription pre-fixed with learn-students- and the resource group student-
3. Configure your virtual machine to the following requirements:
   * Set Region to (US) East US
   * Set Availability Option as Availability zone and availability zone as Zone 3
   * Image as Ubuntu Server 24.04 LTS - x64 Gen2 (If not preselected)
   * Size as Standard_DS1_v2 - 1 vcpu, 3.5GiB memory. You can select it after clicking on See all sizes.
```
Hint
Under instance details:

Region can be changed by clicking the drop-down and selecting the appropriate region - (US) East US may be your default.
Availability can be changed by clicking the drop-down and selecting Availability Zone.
More than one availability zone can be selected; de-select all zones except for Zone 3.
```
4. Step4
   * Configure the username for the administrator account with something you like.
   * Configure a strong password for the account. (e.g. ACflLKAW968!)
5. Step5
   * Go to Disk configuration and set a Standard HDD for the OS disk.
   * Navigate to Networking and set Public IP to None.
6. Before creating your virtual machine, run final validation checks to ensure all configurations meet your requirements and Azure's standards.
7. Under deployment details, how many Resources were generated when you created a virtual machine?
```
Hint
Does your virtual machine meet all of the following requirements:

Region: (US) East US
Availability Option: Availability zone
Availability zone: Zones 3
Image: Ubuntu Server 20.04 LTS - x64 Gen2
Size: Standard_DS1_v2 - 1 vcpu, 3.5GiB memory
OS disk type: Standard HDD (in Disks)
Public inbound ports: None (in Networking)
```
Answer: 4

*That's right! There are 4 different resources created under the two types Microsoft.Compute and Microsoft.Network.*

### Resource Categorization
Understanding the difference between compute, storage and networking is key for anyone working with the cloud. Do you know the difference?

*Congratulations! Knowing the difference between the main storage options will set you up for success!*

---
### Who is responsible?
In Azure, resources typically fall under one of the three cloud service types: Infrastructure as a Service, Platform as a Service, and Software as a Service.    
Answer : IssS

*That's right! IaaS is the most fliexible, and provides the greatest amount of control. Azure is responsible for the hardware, network connectivity and physical security. The customer is responsible for everything else.*
Which of the following offers the Customer the greatest amount of control?

### Analytics vs AI/ML
Azure has a vast ecosystem, including services dedicated to Big Data and Analytics and AI & Machine Learning.

Categorize the following Azure services based on the type of tool category that fall into.
