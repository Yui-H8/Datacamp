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
