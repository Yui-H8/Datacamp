# AWS Concepts
---
### Navigating the AWS console
* In this exercise, you'll login to the AWS Management Console and familiarize yourself with the interface. Additionally, you'll learn how to search for and find key services such as EC2.    
*Note: The sandboxes in this course have been configured to achieve the goals within the exercises therefore some non-related services may be restricted.*
1. Once logged in, you'll enter the AWS Management Console where you will see several different widgets including recently visited services, applications in the current region, getting started information, and much more.
2. This will open up the EC2 dashboard that includes various widgets such as Resources, Instance alarms and more.
3. Under the Resources widget, there are multiple services available. Which service is not included in the list?    
    You won't find billing information on the EC2 dashboard, instead that is located under Billing and Cost Management.
---
### Classifying the benefits of using AWS
*Cost efficiency, Operationnal Flexibility*
   
### Exploring useful services in AWS
1. Cost management is an important aspect of managing your AWS infrastructure, let's explore a service that will help with this crucial function.
* From the console dashboard, use the Search bar to locate Billing and Cost Management. You'll land on the home page which provides insights such as Cost summary, Cost breakdown and more.
* Navigate to the Getting Started page where you'll find a range of topics that can be explored further.

2. Let's explore the topic Budgets and planning.
* Here we can see Common tasks and Other tasks. Common tasks include tools to help estimate workload cost, set up budgets as well as reporting against budget options.

3. Time to look at a popular service in AWS, Amazon S3.
* Navigate to the S3 service page  Review the overview page that includes details such as how it works, benefits and use cases.

4. A service that works well with S3 that you'll explore more in future courses is Amazon CloudFront. CloudFront is a content delivery network used to send content like images, videos and more quickly.
* Navigate to the CloudFront service page Review the overview page that includes details such as how it works, benefits and use cases.
---
### Protecting systems, information, and assets
Spot on! This pillar is all about safeguarding your information, systems, and assets while ensuring your business can continue to deliver value.

### Apply the Well-Architected Framework pillars
* Your company is planning to migrate a mission-critical application to AWS. The application must ensure data protection and compliance with regulations, maintain high availability, and optimize costs.
---
### Cloud adoption strategies with AWS CAFCloud adoption strategies with AWS CAF
6 parts   
* Your organization is preparing for cloud migration, and it's essential to classify strategies based on their alignment with the **AWS Cloud Adoption Framework** (AWS CAF). Your task is to evaluate different approaches and determine which align with AWS CAF principles.

### Exploring migration services
* You are an IT project manager responsible for overseeing your company’s cloud migration to AWS. The initial phase of the migration involves tracking the progress of several teams using different tools and ensuring the timely transfer of your on-premise data to AWS.
* You are evaluating AWS Migration Hub to monitor these processes, and you are exploring the first two steps of setting up an AWS Snowball job to securely move large datasets.

1. First, we'll start by exploring a migration service called AWS Snowball, which is a service that provides secure devices to transfer your data into and out of AWS.
* Navigate to the AWS Snow Family service page.
* Time to review the configuration options in Snowball, start by clicking the button to Order an AWS Snow family device (we will not be completing the configuration or ordering any devices).

2. Provide a name for the data transfer job, such as 'MyFirstImport' For job type, we'll set it to Import into Amazon S3.
