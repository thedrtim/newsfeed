
#  Deploying a NewsFeed Website in the Cloud
![](images/newsfeed.png)

# Introduction
Hey! My friend, Utibe and I built this website. We built the fullstack website that consumes news from a news API and shows the data in the frontend.
There is also an authentication feature that allows users to sign up and saves user's data to an sqlite database.

# THE DEPLOYMENT
I deployed the website on AWS. It runs on EC2 instances as part of an auto scaling group. Here is the URL (will be taken down soon) [link](http://news-feed-load-balancer-49b43ec3921a6792.elb.us-east-2.amazonaws.com/). Now let's look at the table first and thereafter take a high level overview of our infrastructure architecture diagram.

| Resources               | AND       | Purpose                  |
|-------------------------|:---------:| ------------------------:|                
|IAM                      | For       | Assigning Roles          |
|SSM                      | For       | AWS Session Management   |
|Auto-scaling Group       | For       | App scaling              |
|IGW, Nacl, Security Group| For       | Internet Traffic Control |
|Cloudwatch               | For       | Collecting Logs          |
| S3 Bucket               | For       | Storing Logs             |
|Lambda                   | For       | Processing Data          |
|Eventbridge              | For       | Triggering Log collection|



### ![VPC Infrastructure Architecture!](newsfeed.jpg)

I setup a VPC in my AWS account with 2 subnets. Also attached an internet gateway and setup route tables to route traffic within the VPC. Then I created an auto-scaling group that spans multiple availability zones. The whole point of the auto-scaling group is to ensure that our app scales as needed in response to the load on the servers. 

And, oh yeah, in order to balance load across instances...I attached a Network Load balancer. You can refer to the image above for clarification.

Finally, Logs were collected with Cloudwatch and saved in my pre-defined S3 Bucket.


# Project Owner - Timothy Bamiro, Utibe Umanah
