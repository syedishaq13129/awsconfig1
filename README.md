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

![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/b2d1968c-1314-4885-a483-300d50caf3de)

	Optionally, you can specify additional stack options such as tags, IAM roles, and permissions.

	Review the configuration details and click "Next" to proceed.



	On the "Configure stack options" page, you can specify advanced options if needed, but the default settings should suffice for this example.

 ![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/0208913a-b882-47d7-8f98-292c28282d90)





	Click "Next" to proceed to the "Review" page.


![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/29b32ff1-e36b-49a7-b2f2-5fcd633369df)

 
	Review the stack details and click "Create stack" to initiate the deployment.

![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/5b2b461a-dc5d-4135-b6bb-d879114ef851)
![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/22d982a4-cb9b-4fa8-be40-e332a942418b)
![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/2f0590ae-cb4a-4f33-a2b8-74687b0cc0c3)

	Wait for the CloudFormation stack to be created and for the AWS Config rule to be provisioned. You can monitor the progress on the CloudFormation stack events page.

![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/3ab74941-c46e-480d-8aac-459fbb9ab63f)

	Once the stack creation is complete, the AWS Config rule will be active and enforced on your AWS account.

 ![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/d9dad56e-2574-4500-8187-5330f4e88696)
 
	After the deployment, the AWS Config rule "required-tags" will be in effect, ensuring that all EC2 instances have the specified tag with the key "map1key" and value "map001". If any instances are found without this tag, they will be considered non-compliant.

 ![image](https://github.com/syedishaq13129/awsconfig1/assets/122854504/913dda83-ad06-4eff-92bd-41662d495e4b)


Remember to review and customize the code, input parameters, and scope to align with your specific tagging requirements before deploying it to your AWS account.


### Deploying with minimum permissions
To deploy a CloudFormation template that includes a Config rule with a resource tag using an AWS managed rule, you will need the following minimum permissions:

CloudFormation Permissions:
•	cloudformation:CreateStack
•	cloudformation:UpdateStack
•	cloudformation:DeleteStack

AWS Config Permissions:
•	config:PutConfigRule
•	config:PutConfigRuleSuppression
•	config:PutConfigurationAggregator

IAM Permissions:
•	iam:GetRole
•	iam:PassRole (for passing the IAM role to AWS Config)


AWS Resource Tagging Permissions:
•	tag:GetResources


Make sure to attach these permissions to the IAM user or role that will be executing the CloudFormation deployment.

It's important to note that these permissions provide the minimum required access to deploy the CloudFormation stack with the AWS managed rule. You may need additional permissions depending on the resources and services involved in your CloudFormation template.


### Customization
Details on customization that can be done


### How to do the deployment
Details on how to do the deployment

```
Code Snippit 
```

## Validating Deployment
Resource Configuration: Customize the specific resources that the Config rule monitors by specifying resource types, tags, or a combination of both. This is done by configuring the Scope property of the AWS Config rule in the CloudFormation template. You can define the resource types to be monitored (e.g., EC2 instances, S3 buckets) and specify specific tag key-value pairs that the resources must have to be evaluated by the rule.

Rule Parameters: Some AWS managed Config rules have customizable parameters that allow you to further define the rule's behavior. These parameters can be specified in the CloudFormation template. For example, the AWS::Config::ConfigRule resource type allows you to set parameters such as MaximumExecutionFrequency to define how often the rule should be evaluated.

Rule Evaluation Frequency: Customize the frequency at which the Config rule is evaluated by specifying the MaximumExecutionFrequency parameter in the CloudFormation template. You can set it to values such as One_Hour, Three_Hours, Six_Hours, Twelve_Hours, or TwentyFour_Hours. This determines how often the rule's compliance is assessed.

Rule Names and Descriptions: Provide custom names and descriptions for the Config rules in the CloudFormation template to make them more descriptive and identifiable within your AWS environment. You can set the ConfigRuleName and Description properties of the AWS::Config::ConfigRule resource in the template.

Outputs and Stack Outputs: Define outputs in the CloudFormation template to extract information about the deployed resources. For example, you can create an output for the ARN of the created Config rule or any other relevant information you may need.

By utilizing these customizations, you can tailor the behavior and scope of the Config rule to match your specific requirements when deploying it through CloudFormation.
