# Introduction to Azure
---
**Description**

In this course, you will dive into a variety of Azure services, including Compute and Storage, gaining hands-on experience with some of Azure's most powerful and exciting features. Along the way, you'll learn practical skills and daily tasks performed by Cloud Engineers, DevOps professionals, and Cloud Architects to streamline workflows and harness the full potential of the cloud.


This course serves as an engaging introduction and a foundational step toward earning your AZ-204 certification. Let’s get started!

---
### Exploring Azure services
Let's dive into Azure and explore what’s ahead in this course! Azure offers a wide range of services, from data storage to app hosting and automation. Instead of just talking about it, let’s jump in and see it for ourselves.

In this exercise, we'll start by navigating the Azure portal and getting familiar with its interface.
1. Welcome to the Azure Portal

You've been automatically logged into your own Azure account!    
**Note** : You may be prompted with a Getting started page, you can exit out of this to land on the Azure portal home page.

2. In Azure, there are many ways of navigating, lets explore using the Search bar:
   * Navigate to the Virtual Machines overview page using the Search bar
   * In chapter 3, you will be creating your first virtual machine!
3. Let's try the alternative using the Portal menu:
   * In the Portal menu on the top left of the home page to navigate to Storage Accounts.
   * In chapter 2, you will be working with Storage accounts!
4. What pre-fix does the existing Storage account start with?
   Answer: Strage

*Amazing work! Azure makes it really easy to navigate around the portal in so many ways!*

### Exploring a Function app
You're part of the development team at Cipher Coffee, a specialty coffee shop blending innovation with great brews. As the shop expands its digital presence with an online ordering system and a customer rewards app, the team is exploring cloud compute services to support these initiatives.

In Azure, serverless means running code or services without managing the underlying servers, where Azure automatically handles scaling, availability, and infrastructure.

To test serverless computing, a Function App has already been set up. Let's dive in and access the pre-configured Function App to see how it works!

1. Navigate to the Function app section.
2. Lets access your first Function app!
   * In the Function app overview page, open the pre-existing Function app called `cipher-coffee-app-...`    
**Note**: As this is the first time you're accessing the function app it will take some time to initiate.
3. Now that your Function app has initialized:
   * Navigate to the Browse button to open your Function app.
   * You have now successfully launched your first Function App, a serverless solution that runs on demand and scales automatically, no infrastructure management needed!
4. Which of the following best describes an Azure Function App?

*Correct! Azure Function App allows you to run code in response to triggers like HTTP requests, timers, or messages, without managing servers.*

---
### Finding Resource groups
Cipher Coffee has successfully completed one of their projects and now needs to clean up unused resources to avoid unnecessary charges. They’ve tasked you with identifying these no longer needed resources.

In Azure, a resource group is like a container that holds related resources like virtual machines, databases, and storage, making them easier to manage as a unit.
1. Resource groups are essential to managing your resources in Azure.
   * Once logged into the portal, navigate to the Resource groups section.
2. Now that you're at the resource groups overview page:
   * Open the Resource group named `student-...`
3. In the Resource group, how many resources currently exist?
   3

*Correct! Currently there are 3 resources in the Resource group that you're accessing. Great job!*

### Managing Resource groups
Now that you've successfully located the project, it's time to clean up the resources, to prevent Cipher Coffee from incurring any unnecessary costs.
1. Resource groups simplify resource management. In this case, we want to delete the entire group to remove all associated resources at once.    
   In the Resource group, navigate to Delete resource group and select it.
2. Now you have to confirm that you'd like to delete this Resource group:
   * In the pop up menu, copy the name of the resource group.
   * Paste the name of the Resource group to confirm deletion.
   * Confirm the deletion by selecting Delete in the pop up.

A notification will alert you that the resource group is being deleted and will be deleted in a few moments.

3. Why is effective resource management important in a cloud environment?

*Correct! Resource management helps minimize costs, ensure efficient performance, and maintain a secure, well-organized cloud environment.*

### Resources vs Resource groups
Which of the following statements correctly describes the difference between a resource and a resource group in Azure?
```
A resource group is a single cloud service, while a resource is a collection of multiple services.
A resource group automatically scales resources, while individual resources must be manually adjusted.
A resource is used for billing, while a resource group is only for organizing services.
A resource is an individual cloud service, while a resource group is a container that organizes multiple related resources.
```
