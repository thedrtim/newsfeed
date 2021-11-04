# Team Project

## Project: DEPLOY A WEB APP TO THE CLOUD

## Cloud Platform: AWS

### Resources: [IAM, SSM, Internet Gateway, Security Group, Auto-scaling Group, NACL, Lambda Function, Cloudwatch, S3 Bucket]

# NewsFeed
![](images/newsfeed.png)

# Introduction
Hey! I forked this newsfeed website from a friend. He built the fullstack website that consumes news from a news API and shows the data in the frontend. He's quite smart, isn't he?😋.

There is also an authentication feature that allows users to sign up and saves user's data to an sqlite database.

# My Actual Job: DEPLOYMENT
The website is deployed on AWS. It runs on EC2 instances as part of an auto scaling group. Here is the URL (will be taken down soon) [link](ec2-3-14-217-50.us-east-2.compute.amazonaws.com). Now let's take a high level overview of our infrastructure architecture diagram.

![VPC Architecture!](newsfeed.jpg)
I setup a VPC in my AWS account with 2 subnets. Also ttached an internet gateway and setup route tables to route traffic within the VPC. Then created an auto-scaling group that spans multiple availability zones. The whole point of the auto-scaling group is to ensure that our app scales as needed in response to the load on the servers. 

And, oh yeah...I attached a Network Load balancer. You can refer to the image above for clarification.

