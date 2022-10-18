---
title: "SQL Injection"
chapter: false
weight: 51
pre: "<b>6.1 </b>"
---
 
---

#### A SQL injection attack consists of injection of a SQL query via the input data from the client to an application.

---

#### 1. Sign in to [Cloud One](https://cloudone.trendmicro.com/home)
- Select the **Workload Security** tile

![C1WS](/images/Login_C1.png)

---

### 2. Click the Computer tab and locate the DVWA server. 
- Click on the **DVWA** server to open its policy details.
- From the left-hand menu, click **Intrusion Prevention**.
- Change the default configuration from Inherited to **ON**.
- Change the IPS behavior to **Detect** mode.
- Click **Save**.

![WS_Policy](/images/c1ws_1.PNG)
![WS_Policy](/images/c1ws_0.PNG)

---

#### 3. This application is susceptible to SQL injection attempts. We need to be able to report and protect this security concern.

- Keep the DVWA policy details still open.
- From the left-hand menu, click **Intrusion Prevention**.
- Click **Assign/Unassign** to view and add IPS rules specific to this server.
- In the upper right corner, search for the rule <code>1005613 - Generic SQL Injection Prevention - 2</code>
- Select the checkbox to assign rule **1005613 - Generic SQL Injection Prevention - 2**.
- Click **OK**.
- Click **Save** and close the policy details window.

![WS_Policy](/images/c1ws_2.PNG)
![WS_Policy](/images/c1ws_2e5.PNG)

---

#### 4. Now access the DVWA application.
- In the AWS console, navigate to **CloudFormation**.
- Select the Stack named: <code>workload-security-workshop</code>.
- Select the **Outputs** tab.
- Copy the value of **DVWAPublicDNSName** and paste in a new tab of your browser.

![WS_Policy](/images/aws_1.PNG)


---

#### 5. Access the web application using the Public IP/DNS. 
- Remember that it will be over HTTP. 
- User: <code>admin</code>
- Password: <code>password</code>
- **Login**

![WS_Policy](/images/dvwa_login.png)

---

#### 6. Now that you have successfully logged in, Create/Reset Database. 
- Click button: **Create/Reset Database**

{{% notice note %}}
<p style='text-align: left;'>
After Create/Reset you will be logged out of the DVWA. Please login again using same credentials from Step 3.
</p>
{{% /notice %}}

![WS_Policy](/images/dvwa_db_set.png)

---

#### 7. DVWA SQL Injection 
- Select: **SQL Injection**
- User ID: ```admin ' OR 1=1 --' ```

![WS_Policy](/images/sql_1.png)
![WS_Policy](/images/sql_2.png)

---

#### 8. Go back to the Workload Security Console.

- Click on **Events & Reports** tab.

{{% notice note %}}
<p style='text-align: left;'>
It may take a few minutes for the detection and events to appear on the console (~6 min).
</p>
{{% /notice %}}


![WS_Policy](/images/c1ws_4.PNG)
![WS_Policy](/images/c1ws_5.PNG)

---

#### 9. Prevent future SQL injection attempts by returning the IPS module to Prevent.

- Click the **Computers** tab and locate the DVWA server. 
- Click on the **DVWA** server to open its policy details.
- From the left-hand menu, click **Intrusion Prevention**.
- Change the IPS behavior to **Prevent** mode.
- Click **Save**.

![WS_Policy](/images/c1ws_1.PNG)
![WS_Policy](/images/c1ws9.png)

---

#### 10. Repeat the SQL attack.

- Select: **SQL Injection**
- User ID: ```admin ' OR 1=1 --' ```
- Note that the connection has now been reset.

![WS_Policy](/images/sql_1.png)
![WS_Policy](/images/attck_1.PNG)

-----
#### Amazing work, you are now actively protecting this web app from SQL Injections!! The DVWA application holds tons of vulnerabilities.  :rocket: :cloud: