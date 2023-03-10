---
title: "AWS Security Hub"
chapter: true
weight: 40
pre: "<b>5. </b>"
---

# Enable event forwarding to AWS Security Hub

### Deploy the integration between Workload Security and AWS Security Hub

AWS Security Hub provides you with a comprehensive view of your security state in AWS. Security Hub collects security data from across AWS accounts, services, and supported third-party partner products and helps you analyze your security trends to identify the highest priority security issues.
This example application creates the custom integration with AWS Security Hub. With this integration it is possible to send Workload Security events to Security Hub with the use of the SNS.

![Sec_Hub](/images/sns.png)

---

#### 1. Enable your AWS account to leverage AWS Security Hub.
- In the AWS Console, navigate to **Security Hub**.
- Click **Go to Security Hub**.
- Leave the default selections.
- Click Enable **Security Hub**.

![Sec_Hub](/images/sec-hub11.png)
![Sec_Hub](/images/sec-hub12.png)
![Sec_Hub](/images/sec-hub13.png)

---

#### 2. Now launch the provided CloudFormation template below.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=workload-security-hub&templateURL=https://immersionday-workshops-trendmicro.s3.amazonaws.com/workload-security/sec-hub.yaml) 

- Click **Next**.

![Sec_Hub](/images/sec-hub1.png)

---

#### 3. A Cloud One API Key needs to be created to continue deployment.

- On the Cloud One Console home page, click **User Management**
![Sec_Hub](/images/api1.png)

---

#### 4. Select the API Keys tab from the left-hand menu.

- Click **new**
- **API Key Alias**: <code>immersion-day</code>
- **Role**: <code>Full Access</code>
- Click **Next**
- Copy down your **API Key** in a secure location

![Sec_Hub](/images/api2.png)
![Sec_Hub](/images/api3.png)


---

#### 4. Back in the Security Hub CloudFormation tab.
- Paste in your API Key
- Click **Next**

![Sec_Hub](/images/sec-hub2.png)

---

#### 5. Configure Stack Options
- Add Tags (Optional)
- Click **Next**

![Sec_Hub](/images/sec-hub4.png)
![Sec_Hub](/images/sec-hub5.png)

---

#### 6. Review Stack and Deploy
- Check Acknowledge box 
- Click **Create Stack**

![Sec_Hub](/images/sec-hub6.png)
![Sec_Hub](/images/sec-hub7.png)

---

#### 7. Wait for the stack to reach complete status.

![Sec_Hub](/images/sec-hub8.png)
![Sec_Hub](/images/sec-hub9.png)

---

#### 8. Select the Outputs tab.
- Copy down the values for:
    - AccessKey
    - SNSTopic
    - SecretKey

![Sec_Hub](/images/sec-hub10.png)

---

#### 9. Navigate to the Cloud One Workload Security console.

- Click the tab **Administration**
- From the left-hand menu, select **System Settings**.
- Select **Event Forwarding** from the system settings tabs.
- **Check the box** to publish event to Amazon SNS.
- Under **Access Key**, paste in the value from the previous step.
- Under **Secret Key**, paste in the value from the previous step. 
- Under **Amazon SNS**, paste in the value from the previous step.
- Click **Test credentials and send notification**.
- Click **Save** in the lower right corner.

![Sec_Hub](/images/sec-hub3.png)


--------

#### Congrats on your custom Security Hub integration from Workload Security we will generate events in the labs ahead.:star-struck: :robot: :white_check_mark: :cloud:


