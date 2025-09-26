# AWS Cloud Technology and Services Concepts
---
### Exploring the UI
1. Once logged in,, you'll have access to the AWS Management Console. Here, you'll see several different widgets, including recently visited services, applications in the current region, getting started information, and much more.
2. Here, you'll see a list of all the various services AWS offers. You'll work with a number of services in this course, including EC2, S3, Elastic Container Service, and more.
3. Which of the following services is not part of the _Compute_ category?    
*Answer*    
Elastic Container Service (ECS) falls under the containers category, offering a fully managed container orchestration service.
---
### Selecting the right instance type
You are a cloud engineer looking to migrate a financial modeling application to AWS.    
Which of the following EC2 instance types is most suitable?
* Storage-optimized instances are better suited to applications that require high storage and low-latency access.
* General Purpose: As you might have guessed, this instance type is more suitable for general-purpose applications such as web servers and code repositories.
*Answer*
Compute-optimized instances are an excellent fit for compute-intensive workloads such as financial and scientific modeling applications.

### Launching a Web Server on EC2
1. Let's launch our first web server. Use the search bar to navigate to the EC2 services page. Click on Launch instance from the EC2 dashboard, and name this "MyFirstWebServer."
2. We can now start configuring our web server, we'll start by configuring our Amazon Machine Image under the Applications and OS Images header. To begin, we can apply the following configuration from the dropdowns:
* Amazon Machine Image: Amazon Linux 2023 AMI
* Architecture: 64-bit (x-86)
3. We can configure our Instance type and Key pair (login) settings next. The instance type refers to compute power, memory and networking capacity. A key pair helps us securely connect to our instance.
* Set the instance type to t2.small in the dropdown.
* Create a new key, by selecting Create new key pair and filling out the following details:
* Key pair name: "WebServerEC2"
* Key pair type: RSA
* Private key file format: **.pem **
4. Note; DataCamp has configured the Network settings inline with our policies, so we will utilize the default security group.
* Update the Firewall (security groups), select existing security group button.
* The security group should be set to "default"
5. No changes will be made to the storage for our instance. Instead, explore the Advanced details section. Skip over the various options until you reach the User data header.
    
In this section, we can provide commands or command scripts that will run when the instance is launched. Open the bash.txt file from the Resources folder on the Desktop. Copy and paste the script into the User data section.
6. Good job, you've configured all settings for our web server. Launch the instance from the Summary pane.

     
*By defining the instance we are specifying the hardware that the instance will utilise. Each instance type offers different compute, memory and storage capabilities and are grouped into instance families such as general purpose, compute optimised etc.*
---
### Load balancing vs Auto-scaling
You are a Solutions Architect leading two specialized teams within your organization.

Team A is responsible for implementing a robust load balancing architecture for your servers.   
Team B is tasked with creating an efficient auto-scaling solution to handle dynamic changes in demand for the servers.   
You have a set of deliverables that you need to divide among the two teams.   
* Load balancing
* Auto scaling

*Load balancing and auto-scaling will ensure your compute is scalable and cost efficient.*
### Setting up a launch template
1. As a Cloud Administrator, you've been tasked with setting up an EC2 launch template to be used for Auto Scaling.
   
A launch template helps streamline EC2 provisioning by allowing users to define reusable configurations with settings such as Amazon Machine Image and Instance type. Your overall goal is to ensure that instances can automatically scale up or down based on demand, ensuring high availability for your application.
> Before we setup our auto-scaling group, we first need to create a launch template which will contain the configuration information to launch an instance including the ID and Amazon Machine Image. When used with Auto Scaling, these templates ensure that new instances are automatically launched with consistent settings as demand changes, enhancing application performance and resource efficiency.
* Navigate to the Launch Templates page on the EC2 Dashboard, and select Create launch template.

2. The interface for a launch template is very similar to setting up an EC2 instance except for the first step, defining the Launch name and description.
* Provide a useful launch template name, such as "MyWebServerTemplate"
* Provide a useful launch template description such as "A re-usable web server template for setting up different environments."

3. Let's configure our launch template in two sections, first we'll configure the Amazon Machine Image and Instance type.
* Amazon Machine Image: Amazon Linux 2023 AMI
* Instance type: t2.small

4. Next, we'll move into configuring our key pair and firewall settings; in this example, we will not include the subnet.
* Key pair: Create new key pair
* Key pair name: "WebServerEC2Template"
* Key pair type: RSA
* Private key file format: .pem
* Subnet: Do not include in template
* Firewall: Select existing security group: default

5. Once you have filled out the configuration settings for this launch template, so we can setup our Auto Scaling group.

6. How does an EC2 launch template contribute to Auto Scaling functionality?

*Correct! You've successfully grasped how an EC2 launch template integrates with Auto Scaling. By understanding how the template defines the instance settings and Auto Scaling adjusts the number of instances, you're now ready to manage scalable, efficient cloud infrastructure.*


### Auto-scaling your instances
You are a Cloud Administrator responsible for ensuring your web application can handle varying traffic loads. Your task is to set up an Auto Scaling Group that automatically adjusts the number of EC2 instances based on the current demand, ensuring high availability and cost efficiency.
