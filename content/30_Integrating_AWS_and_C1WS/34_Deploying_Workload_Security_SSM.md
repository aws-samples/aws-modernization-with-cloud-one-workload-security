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

#### 2. In the AWS console, navigate to **Systems Manager**.
- In the left-hand menu, under Application Management select **Parameter Store**.
![ssm](/images/create_param.png)

#### 2.1 We need to create 4 parameters using the values copied previously.

#### Parameter 1:

- Click **Create Parameter**.
- Name: <code>dsManagerUrl</code>
- Value: <code>https://app.deepsecurity.trendmicro.com:443</code>
- Click **Create Parameter**.
![ssm](/images/create_param4.png)

---

#### Parameter 2:

- Click **Create Parameter**.
- Name: <code>dsActivationUrl</code>
- Value: **<code>dsm://agents.deepsecurity.trendmicro.com:443/</code>**
- Click **Create Parameter**.
![ssm](/images/create_param1.png)

---

#### Parameter 3:

- Click **Create Parameter**.
- Name: <code>dsTenantId</code>
- Value: **<code> Paste the tenantID value copied from step 1.1 </code>**
- Click **Create Parameter**.
![ssm](/images/create_param2.png)

---

#### Parameter 4:

- Click **Create Parameter**.
- Name: <code>dsToken</code>
- Value: **<code> Paste the token value copied from step 1.1 </code>**
- Click **Create Parameter**.
![ssm](/images/create_param3.png)

#### Your parameter store should have the following 4 parameters created now.
![ssm](/images/create_param5.png)

---

#### 3. In Systems Manager, on the left-hand menu, under Node Management select **Distributor**.
- Select **Third Party** tab.
- Search: <code>TrendMicro-CloudOne-WorkloadSecurity</code>
- Select the Package.
- Click on **Install on a Schedule**.
![ssm](/images/ssm1.png)

---

#### 4. Create Association.

Provide association details.

- Name: <code>workload-security-distributor-workshop</code>

Document.

- Do not edit the document Section.

Parameters.

- Installation Type: **In-place update**

Target Selection.

- Target Slection: **Specify instance tags**
- Tag Key: <code>Project</code>
- Tag Key: <code>Cloud One Demo Lab</code>
- Click **Add**.

Specify Schedule.

- Select **No Schedule**.

Leave the default selection for the rest.

- Click **Create Association**.

![ssm](/images/ssm2.png)
![ssm](/images/ssm3.png)
![ssm](/images/ssm4.png)

---

#### After a few minutes, refresh the page to ensure the deployment association is successful.
![ssm](/images/ssm5.png)

---

#### 5. Verify your server fleet is now managed and has the appropriate security policy automatically assigned.
- Navigate to **Cloud One - Workload Security**.
- Click the **Computers** tab.

Here you get complete visibility into the server fleet status. (Optional) Even more information can be displayed by clicking **columns**.

![ssm](/images/ssm6.png)

---

> **Et voila, we just automated the deployment of multiple Workload Security Agents in our AWS environment** 🤩 :cloud: 🤖 :rocket: