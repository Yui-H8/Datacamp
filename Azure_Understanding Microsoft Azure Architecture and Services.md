# Understanding Microsoft Azure Architecture and Services
---
### Prepare for Azure cloud usage
* Imagine you are working for a company looking to start using Azure cloud.
* What is the initial step you must take when planning to use Azure cloud resources?
Create an Azure account

### Azure physical infrastructure
* Please choose all accurate statements regarding Azure's physical infrastructure.
- Azure's physical infrastructure consists of a global network of data centers located around the world.   
- An Azure region is a geographical region that contains a one or more data centers offering Azure services.    
- Azure availability zones are separate, physically independent data centers within a region.

### Azure hierarchical structure
* The hierarchical structure of Azure refers to the way resources can be organized in a hierarchy, allowing for a structured and organized management approach.   
The hierarchy typically involves several levels.
---
### Storage account functionality
### The right storage service
* Azure storage services are cloud-based storage services that provides scalable and secure data storage solutions, suitable for various data storage needs.

### Table storage use cases
* Azure provides an extensive array of data storage services designed for diverse real-world scenarios, spanning from simple applications to more complex architectures and data processing workflows.
- Tables provide faster and more scalable access to large amounts of unstructured data, such as key-value pairs.
- Azure tables service allows you to store and retrieve data in a flexible, schema-less way.
---
### Create storage accounts
* Once logged in, you'll enter the Azure homepage which provides an overview of popular services as well as recently used resources, and quick start options.
---
*Platform on the screen*
### Create storage accounts
* You are an IT engineer in a company that aims to establish a shared space on Azure for storing, editing, and downloading documents.    
You advise them to opt for different storage account for each department to align to their requirements.     
The manager agrees with your recommendation and requests you to set up a storage account with the specified configuration.     
They need two storage accounts, one for Finance department and the other one for Marketing.
1. Once logged in, you'll enter the Azure homepage which provides an overview of popular services as well as recently used resources, and quick start options.
   
*Note: depending on your regional settings, your Azure Portal might be displayed in another language. To quickly change the language to English, click the gear icon at the top right, select the third tab on the left (about language and region), and then change the language appropriately.*

2. Create a new storage account called "finance" and a suffix of your own to make it unique.    
Use East US as region and make it zone-redundant.

3. Create a second storage account called "marketing" and a suffix of your own to make it unique.   
Use East US as region and make it locally-redundant.

### Remove storage account
* The Finance department decide they will not use a storage account until later on.     
To minimize associated costs, the manager has requested the removal of the storage account.

1. There should be an existing storage account called "finance***" from the previous exercise.
---

### Redundancy hierarchy
