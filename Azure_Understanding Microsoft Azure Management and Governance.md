# Understanding Microsoft Azure Management and Governance
---
**Description**

This course is the third course in preparing you for the Azure Fundamentals (AZ-900) exam. Through interactive exercises and videos, you will learn about managing and governing resources in Microsoft Azure, focusing on tools for resource management, cost control, and security. Key topics include Azure Resource Manager (ARM), role-based access control (RBAC), cost management, and monitoring.

---
### Azure resources vs. services
You'll often encounter 'resources' and 'services' when working with Azure. They are both important building blocks in Azure.

What is the difference between a resource and a service?
```
〇 A service is a set of features in Azure, and a resource is the product or object of a service.
A resource and a service are the same thing in Azure.
A resource is a set of features in Azure, and a service is the product of a resource.
```
*That's right! Services and resources are important building blocks of Azure; we'll talk about both often throughout the course.*

### Possible use cases for management and governance
Azure provides you with a set of services to help you with the management and governance of your data, applications and other resources in Azure.

Which of the options below are possible use cases for the Azure management and governance services? Select all that apply.
```
〇 Implement data protection standards
〇 Manage resources of web applications, such as a dashboard
〇 Analyze the performance of web applications
〇 Optimize costs to avoid overspending
```
*Well done! All these options are indeed specific use cases for which you can use Azure. It is a comprehensive cloud platform with a lot of functionality.*

### Use case: dashboard performance
You are in charge of the management and governance of a web application in Azure. The application consists of a dashboard with regularly updated financial performance data, displaying real-time information on revenue, expenses, and profit margins.

Which statements are true or false with respect to your use of Azure?

*Well done! You now know more about how Azure management and governance can be relevant for different use cases and tasks. In the following videos and exercises, we'll go deeper into cost management and governance.*

---
### Regional differences in compliance
Can you take into account regional differences when using Azure for compliance?
```
No, this is not possible in Azure
〇 Yes, Azure supports regional differences in compliance
Yes, but only with the help of a third-party application from Azure Marketplace
Yes, but this is only available for the US and Europe
```
*Perfect! You can take into account regional differences in compliance and data protection with the help of Azure Regions. These are geographical areas where the physical Azure data centers reside. Azure also uses them to define boundaries for data residency and compliance.*

### Concepts of cost management and governance
In the video, we saw some important concepts related to cost management and governance in Azure.

In this exercise, we'll put your knowledge to the test by linking these concepts to the right description.

Link the following key words to the right descriptions by placing them in order.
1. Governance
2. Azure Marketplace
3. Compliance
4. Pay-as-you-go

*Well done! Understanding these concepts is important to also understand how Azure can be applied to help you with specific use cases, such as in the next exercise!*

### Use case: managing budgets
You are working for an e-commerce company that uses Azure as its cloud solution. The company would like to ensure cost efficiency, monitor spending, and allocate costs across different departments and projects.

Which tasks can you do with the help of Azure? Select all that apply.   
To help you along, you can explore the prompts to learn more about the main features of cost management in Azure.

**Budget management**

Establish and manage budgets to control spending within predefined limits. Set up alerts to receive notifications when actual spending approaches or exceeds budget thresholds.

**Financial control and optimization**

Manage costs effectively, ensuring you have the tools needed to optimize spending, maintain financial control, and align cloud resources with business objectives.

**Cost analysis**

Access detailed cost analysis tools and custom reports to understand spending patterns across different Azure services. Visualize cost data to identify areas for optimization.

**Manage Azure spending**

Enable proactive monitoring and control over Azure spending, helping organizations stay within budget constraints.

*Well done! Another example of a task would be to manage resource usage and monitor costs to identify optimization opportunities. You'll learn more about resource management and monitoring in the next video.*

---
### Benefits of Infrastructure as Code (IaC)
Azure makes extensive use of Infrastructure as Code (IaC) principles. IaC is a practice that involves managing infrastructure resources using code and automation tools rather than manual processes.

What are the main benefits of using IaC for Azure resources? Select all that apply.
```
〇 Provides consistency and reproducibility
〇 Makes it easier to document and share knowledge
Easy to learn
〇 More efficient and less error-prone
```
*Well done! IaC allows standardized and automated infrastructure management, resulting in increased consistency and efficiency while reducing errors and improving collaboration.*

### Resource tags and resource locks
Azure has two important features for managing resources: resource tags and resource locks.

These features help you organize resources and apply metadata to help identify and protect them. You're likely to make use of them for a wide range of tasks.

*Congratulations! Both resource tags and locks are complementary; for example, you could tag resources as 'critical' and then apply locks to prevent deletion or modifications.*

### Use case: monitoring with Azure
You are part of a data project. Your team is considering a migration to Azure. One of the key reasons for this move is Azure's comprehensive features for monitoring the project's resources and applications. You need to present your case to management.

Which arguments could you put forward to convince management of the advantages of monitoring with Azure? Select all that apply.

To get you started, you can ask ChatGPT: 'Why is monitoring with Azure important? Name five key reasons'.

> Why is monitoring with Azure important? Name five key reasons
> **Security**: Monitoring with Azure allows organizations to detect and respond to security threats in real-time, helping to protect sensitive data and prevent breaches.
> **Performance optimization**: Monitoring helps organizations identify and address performance issues, ensuring that applications and services run smoothly and efficiently.
> **Cost management**: By monitoring resource usage and performance, organizations can optimize their Azure spending and avoid unnecessary costs.
> **Compliance**: Monitoring with Azure helps organizations ensure that they are meeting regulatory requirements and industry standards, reducing the risk of non-compliance penalties.
> **Proactive problem-solving**: Monitoring allows organizations to identify and address issues before they impact users, helping to maintain a positive user experience and minimize downtime.

*Excellent! The advanced monitoring that is available in Azure is one of its main strengths. In the following chapter, we'll dive deeper into cost management and governance.*

---
### Create a resource
You are part of a project team that creates machine learning applications (ML apps) supported by Azure. Your first task is to create the first resource for the project, a virtual machine (VM). You have received the following minimum requirements for the VM:

the region should be 'East-US' for cost optimization
its size should be set to the lowest option
authentication for the administrator should be set to password

1. From the Azure Portal, click on Create a resource and create a new virtual machine.
2. Fill in the required settings of the virtual machine as follows and leave the other settings at their default value.
   * Subscription: select the only available option
   * Resource group: select the available resource group (student-)
   * Virtual machine name: "vm-01"
   * Region: (US) East US
   * Size: click on See all sizes and select the first available option (DS1_v2).
   * Authentication type: password
   * Username: "student-dc"
   * Password: "AFmgDCvm258!" 
3. Go to Disks and set Standard HDD as the OS disk. Go to Networking and set Public IP to None.
4. Go to the tab Tags and fill in the following tag.
   * Name: "project"
   * Value: "ML-apps"
   * You can ignore the pop-up about a recommendation for the region if you see one.
5. Go to the Review + Create tab to validate and create the virtual machine.
   * If there is an error it might be because there is no virtual network. If necessary, navigate to Networking and create a Virtual Network with settings of your choice.
   * Make sure the Public IP setting right below is set to None.
6. What are resource tags mainly used for?
