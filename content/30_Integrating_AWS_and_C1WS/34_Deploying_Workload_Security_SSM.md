---
title: "Automate agent deployment"
chapter: false
weight: 33
pre: "<b>4.3 </b>"
---


#### 1. In the Cloud One Workload Security console.
- Click **Support**.
- Select **Deployment Scripts**.

![ssm](/images/deployment_script1.png)

##### 1.1 Locate the 2 parameters described below:
Leave the default selections and scroll to the bottom of the bash script provided.

- Copy down the **tenantID**.
- Copy down the **token**.

![ssm](/images/deployment_script2.png)
![ssm](/images/deployment_script4.png)

---

#### 2. Integrating the Workload Security Agent with AWS Lambda

Automation process to deploy, activate, and check the Deep Security Agents using Lambda function and State Manger Association from AWS. By integrating Workload Security with AWS Lambda, you can distribute Deep Security Agents across multiple platforms.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=workload-security-agent-automation&templateURL=https://aws-workshop-c1as-cft-templates.s3.amazonaws.com/agent-automation.yaml)

![ssm](/images/lambda1.png)

---

#### 2.1 Use the tenant and token parameters collected prior.

- Paste in the **tenant id** value
- Paste in the **token** value
- Click, **Next**, 
- Review stack and check the box to confirm.
- Click **Deploy**.

![ssm](/images/lambda3.png)
![ssm](/images/lambda4.png)

---