# Repository Name 

AWS Config Resource Tag Rule Setup


## On this Page
- [Architecture Overview](#architecture-overview)
- [Prerequisites](#prerequisites)
- [Deployment Guide](#deployment-guide)
  - [Deploying with minimum permissions](#deploying-with-minimum-permissions)
  - [Customization](#customization)
  - [How to do the deployment](how-to-do-the-deployment)
- [Validating Deployment](#validating-deployment)

Add more content if required



## Architecture Overview
Architecture of the solution

## Prerequisites:

Before you begin, ensure that you have the following prerequisites in place:

1) An AWS account with sufficient permissions to create AWS CloudFormation stacks and enable AWS Config recording.
2) AWS Command Line Interface (CLI) installed and configured with your AWS credentials.
3) AWS Config recording enabled. This is required for AWS Config to capture and monitor resource configuration changes. Follow the steps below to enable AWS Config recording:

  •	Open the AWS Management Console and navigate to the AWS Config service.
  •	Click on "Get started" if you haven't set up AWS Config before.
  •	Select the AWS resources you want AWS Config to record changes for.
  •	Choose the delivery method for AWS Config configuration snapshots (e.g., Amazon S3 bucket).
  •	Configure the recording options such as recording frequency and resource types.
  •	Enable AWS Config recording




## Deployment Guide
Deployment Guide (Console Management)
To deploy this CloudFormation template and create the AWS Config rule, you can follow these steps:
	Open the AWS Management Console and navigate to the CloudFormation service.

![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/8e38bb0f-2ccd-4e03-ace6-02d0cfd3a7ca)


	Click on "Create stack" with new resources (standard).

	Select "Template is ready" and "Upload a template file."

![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/4043c17d-a8d8-4a98-9dc8-fa65a9f905ed)


 

	Upload the YAML file containing the code you shared.

	Click "Next" to proceed to the stack configuration page.
                                                              
	Provide a stack name for identification.

 

	Optionally, you can specify additional stack options such as tags, IAM roles, and permissions.

	Review the configuration details and click "Next" to proceed.



	On the "Configure stack options" page, you can specify advanced options if needed, but the default settings should suffice for this example.

 




	Click "Next" to proceed to the "Review" page.



 


                                            










	Review the stack details and click "Create stack" to initiate the deployment.

	 

 

 

	Wait for the CloudFormation stack to be created and for the AWS Config rule to be provisioned. You can monitor the progress on the CloudFormation stack events page.


 

	Once the stack creation is complete, the AWS Config rule will be active and enforced on your AWS account.

 


	After the deployment, the AWS Config rule "required-tags" will be in effect, ensuring that all EC2 instances have the specified tag with the key "map1key" and value "map001". If any instances are found without this tag, they will be considered non-compliant.

 

Remember to review and customize the code, input parameters, and scope to align with your specific tagging requirements before deploying it to your AWS account.


### Deploying with minimum permissions
Details on the permission required to run the scripts

### Customization
Details on customization that can be done


### How to do the deployment
Details on how to do the deployment

```
Code Snippit 
```

## Validating Deployment
Details on how to validate the deployment
