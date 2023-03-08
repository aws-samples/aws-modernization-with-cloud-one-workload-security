---
title: "Creating the base AWS Environment"
chapter: false
weight: 31
pre: "<b>4.1 </b>"
---

---

## 1. Creating the base AWS environment using AWS CloudFormation Template

You can use the CloudFormation template below to create the infrastructure in the same AZ with the 2 subnets, NAT Gateway, Internet Gateway, and EC2 instances.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=workload-security-workshop&templateURL=https://immersionday-workshops-trendmicro.s3.amazonaws.com/workload-security/CFT_Workload_Security_Workshop.yml)

---

### 2. Click on **Next**

![C1WS](/images/create_env_3.png) 

---

### 3. Specifying additional stack parameters

{{% notice info %}}
<p style='text-align: left;'>
A Key Pair is required before continuing this CloudFormation deployment. If you need help creating a Key Pair -> <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair" target="_top">Create a key pair</a>
</p>
{{% /notice %}}


<details>
  <summary> -> <code>CLICK HERE</code> to see how to create a key pair</summary>

**AWS Console -> EC2 -> Key Pairs -> Create key pair**

![C1WS](/images/create_env_9.png) 

</details>
<br>

- **Stack Name:**  <code>workload-security-workshop</code>

- **InspectionVPCCIDR:** the CIDR that you want to use for the VPC. You don't need to change it if you don't want to change the default configuration.
    
- **KeyPair:** Your KeyPair name.

- **MyPublicIP:** Your public IP in CIDR. (e.g. 191.162.228.91/ 32) . You can grab it using a few tools or websites (https://ipinfo.io/ip). It will be used to only allow your IP to access the vulnerable application (DVWA)

- **ProtectedPrivateSubnetAZ:** the AZ that you want to use for your Private subnet.

- **ProtectedPrivateSubnetCIDR:** the CIDR that you want to use for the Private subnet. You don't need to change it if you don't want to.

- **ProtectedPublicSubnetAZ:** the AZ that you want to use for your Public subnet.

- **ProtectedPublicSubnetCIDR:** the AZ that you want to use for your Public subnet. You don't need to change it if you don't want to.

---

### 3.1. Stack details example:

![C1WS](/images/create_env_4.png) 

---

### 4. Configure stack options

Leave fields as default and click **Next**, or optionally define tags to the environment if desired.

![C1WS](/images/create_env_5.png) 

---

### 5. Review the template parameters 
- Mark the checkbox the **"I acknowledge... "**
- Click on **Create Stack**

![C1WS](/images/create_env_6.png) 

![C1WS](/images/create_env_7.png) 

![C1WS](/images/create_env_8.png) 

---

### 6. Follow up the events during creation of the stack.
- Select the **Events** tab
- Click **Refresh**

![C1WS](/images/create_env_10.png) 

---

### 7. Ensure the stack status has reached **Create_Complete**. 
- Select the **Stack info** tab

![C1WS](/images/create_env_11.png) 

---

#### 8. Verify your server fleet is now showing up within Cloud One Workload Security.
- Navigate to **Cloud One - Workload Security**.
- Click the **Computers** tab.

Here you get complete visibility into the server fleet status. (Optional) Even more information can be displayed by clicking **columns**.

![ssm](/images/BaseEnv.png)

---

> **Et voila, we just automated the deployment of multiple Workload Security Agents in our AWS environment** 🤩 :cloud: 🤖 :rocket: