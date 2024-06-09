**AWS Cost Optimization: Automating EBS Snapshot Management with Lambda**

**Overview**
This project focuses on optimizing AWS costs by automating the management of EBS snapshots using AWS Lambda and Boto3. The goal is to identify and delete obsolete snapshots, thus reducing unnecessary storage costs.

**Problem Statement**
AWS EBS snapshots are often created for backup purposes. However, when EC2 instances or their associated volumes are deleted, these snapshots can remain, incurring costs without providing any value. This project addresses the following scenarios:

The EC2 instance is deleted, but snapshots remain.
Both the EC2 instance and its volume are deleted, but snapshots remain.
Snapshots that are not attached to any active volume or instance are useless and should be deleted to optimize costs.

**Solution**
We implemented an AWS Lambda function to automate the following steps:

Fetch all EBS snapshots: Retrieve a list of all snapshots owned by the account.
Filter snapshots: Identify snapshots not attached to any active volumes or instances.
Delete obsolete snapshots: Remove snapshots that are no longer needed.
The Lambda function is event-driven and can be triggered using AWS CloudWatch.


**Components**
Lambda Function: Written in Python using Boto3 to interact with AWS APIs.

CloudWatch: Used to schedule and trigger the Lambda function.

**Prerequisites**

AWS Account, 
AWS CLI configured with appropriate permissions, 
Python 3.x, 
Boto3 library
