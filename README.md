# Single Account Security Accelerator

Security is the Top Priority at AWS, and The _Single Account Security Accelerator_ is a collection of best practices to improve your security posture in a single-account environment. While we recommend that all of our customers embrace a multi-account architecture as mentioned in our [Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html), we recognize that not everyone is able to do so. 

By deploying this CloudFormation template, you will be enabling many of the recommended best practices, such as:
- Enabling [GuardDuty](https://aws.amazon.com/guardduty/)
- Enabling [AWS Config](https://aws.amazon.com/config/)
    - Deploying the [Operational Best Practices for CIS AWS Foundations Benchmark](https://docs.aws.amazon.com/config/latest/developerguide/operational-best-practices-for-cis_aws_benchmark_level_1.html)
- Setting up notifications from GuardDuty on a regular basis for new findings
- Enabling [Security Hub](https://aws.amazon.com/security-hub/)

## How to implement in your account

- Download this [cloudformation template](#linkhere)
- Log in to your AWS Console
- Open CloudFormation
    - *images*?
- Go to Stacks
- Create a stack with new resources
- Select this template via "Upload a template"
- Specify the name of the stack (for future reference), your preferred email address to receive security notifications, and the frequency you'd like to receive emails (to [Cron specifications](https://docs.aws.amazon.com/lambda/latest/dg/services-cloudwatchevents-expressions.html))

## Components deployed in this package
For you reference, we leverage the following Amazon services in this template:
- Amazon GuardDuty
- AWS Config
- AWS Security Hub
- Amazon Simple Notification Service
- AWS Lambda
- Amazon EventBridge
- Service roles for these services


## Post-installation notes

- You can view the outputs of the cloudformation stack to see what was enabled as part of the template for your own awareness.  
- GuardDuty immediately provides protection for your AWS account. If this is your first time activating GuardDuty, it may take some time for the machine learning to understand your account and baseline anomolies. 
  - Also to note, if this is your first time you have 30 days of free GuardDuty protection

## Average Spend
GuardDuty and Security Hub have a 30 day trial period for accounts that have not utilized GuardDuty or Security Hub in the past. Otherwise, this solution was designed with efficiency in mind, and you can visit the [AWS Calculator](https://calculator.aws/) for more information.

## How to revert these changes
If this solution doesn't meet your needs, or if you would rather migrate to a multi-account structure rather than install of this in a single account, you can delete the stackset by:
- Going to CloudFormation
- Selecting the stack name that you created during the install proccess and then push delete

## Roadmap
If you have ideas for releases in the future, we're open to feedback to improve the solutions we create for our customers. 

## Authors and acknowledgment
This was created by Jeremy Schiefer, Brian Galloway, and Anthony Harvey of Amazon Web Services.
