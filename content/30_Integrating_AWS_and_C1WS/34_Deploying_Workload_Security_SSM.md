---
title: "Automate deployment with AWS SSM"
chapter: false
weight: 34
pre: "<b>4.4 </b>"
---

<div class="notices warning" ><p style='text-align: left;'>
<b>Do not continue with these steps if you have already deployed the Workload Security Agent using the Lambda automation. The WS Agent AWS SSM is an alternative deployment method.</b>
</p>
</div>

### Integrating the Workload Security Agent with AWS Systems Manager Distributor

AWS Systems Manager Distributor is a feature integrated with AWS Systems Manager that you can use to securely store and distribute software packages in your accounts. By integrating Workload Security with AWS Systems Manager Distributor, you can distribute Deep Security Agents across multiple platforms, control access to managed instances, and automate your deployments.

---

#### 1. In the Cloud One Workload Security console.
- Click **Support**.
- Select **Deployment Scripts**.

![ssm](/images/deployment_script1.png)

##### 1.1 Locate the 4 parameters described below:
Leave the default selections and scroll to the bottom of the bash script provided.

- Copy down the **manager URL** : <code>https://app.deepsecurity.trendmicro.com:443</code>
- Copy down the **activation URL**: <code>dsm://agents.deepsecurity.trendmicro.com:443/</code>
- Copy down the **tenantID**.
- Copy down the **token**.

![ssm](/images/deployment_script2.png)
![ssm](/images/deployment_script3.png)
![ssm](/images/deployment_script4.png)

---

#### 2. Lets launch the stack to input parameters we collected from Cloud One for Parameter Store **Systems Manager**.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=workload-security-workshop-SSM&templateURL=https://immersionday-workshops-trendmicro.s3.amazonaws.com/workload-security/c1-ws-ssm.yaml)

- Click on **Next**.
![ssm](/images/SSMstack1.png)

#### 2.1 Lets input the parameters.



- Input **activation URL** for **dsActivationUrl** Parameter

- Input **manager URL** for **dsManagerUrl** Parameter

- Input **tenantID** for **dsTenantId** Parameter

- Input **token** for **dsToken** Parameter

![ssm](/images/SSMStack2.png)

#### 2.2 Once the parameters are filled in, click on **Next**.

![ssm](/images/SSMStack3.png)

- Click on **Next**

![ssm](/images/SSMStack4.png)

- Click on **Submit**

![ssm](/images/SSMStack5.png)

- Please wait for the CloudFormation template to complete.

![ssm](/images/SSMStack6.png)

- Once the Cloudformation is complete, please navigate to System Manager- Parameter Store. Within Parameter Store we will see the four parameters that was created.

![ssm](/images/SSMStack7.png)





---

#### 3. Verify your server fleet is now managed and has the appropriate security policy automatically assigned.
- Navigate to **Cloud One - Workload Security**.
- Click the **Computers** tab.

Here you get complete visibility into the server fleet status. (Optional) Even more information can be displayed by clicking **columns**.

![ssm](/images/ssm6.png)

---

> **Et voila, we just automated the deployment of multiple Workload Security Agents in our AWS environment** 🤩 :cloud: 🤖 :rocket: