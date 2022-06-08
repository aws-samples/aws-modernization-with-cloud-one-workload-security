---
title: "Security Hub Insights"
chapter: false
weight: 54
pre: "<b>6.4 </b>"
---
 
---

#### With every attack attempt taken on the previous labs an event has been generated. Created earlier in this workshop was an integration to relay all events from Cloud One - Workload Security to AWS Security Hub. 

---

#### 1. Navigate to the AWS Security Hub console.

- Here you can view your summary for all aggregated data.
- Scroll down under the **insights** section
- Click **EC2 instances with the most findings**.

![WS_Policy](/images/insight1.png)
![WS_Policy](/images/insight2.png)

---

#### 2. Here you will find the 3 instances successfully attacked and then protected in the earlier hands-on labs.
- Select any of the instance Resource ID's to view more detailed information.

![WS_Policy](/images/insight3.png)

---

#### 3. When selecting a specific instance you can see all event findings related to this machine.
- The below example depicts the instance that was affected by a Ransomware attack.
- By selecting one of the finding event's **Title** you can gain clarity on the attacks.

![WS_Policy](/images/insight4.png)
![WS_Policy](/images/insight5.png)


-----
#### Way to aggregate all your server event findings to a localized console! Workload Security can also send event findings to SIEM servers as well. 