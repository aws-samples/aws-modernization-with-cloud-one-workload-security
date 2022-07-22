---
title: "Event-Based Task setup"
chapter: false
weight: 32
pre: "<b>4.2 </b>"
---

### Automatically perform tasks when a computer initiates activation

Event-based tasks let you monitor protected computers for specific events and perform tasks based on certain conditions.

----

#### 1. The first created event-based task will automate the assignment of our Linux security policy to only Linux OS Platforms.  

In Workload Security, create an event-based task.

- Click **Administration > Event-Based Tasks > New**. 


![EBT](/images/ebt1.png)

---

#### 2. The wizard that appears will guide you through the steps of creating a new task. You will be prompted for different information depending on the type of task.

- Select **Agent-Initiated-Activation**.
- Click **Next**.

![EBT](/images/ebt2.png) 

---

#### 3. Edit the event configuration as follows:
- Check the box for **Assign Policy**
- From the drop-down select **Base Policy > Linux**
- Click **Next**

![EBT](/images/ebt3.png)



---

#### 4. Specify the following match condition:
- From the left drop-down menu, select **Platform**.
- From the right drop-down menu, enter ```.*Linux.*```
- Click **Next** 

![EBT](/images/ebt4.png) 

---

#### 5. Review the Event-Based Task.
- Name: <code>Agent Activation- Linux</code>
- Ensure the Check Box is select next to **Task Enabled**
- Click **Finish**

![EBT](/images/ebt5.png) 

---

#### 6. Create a second Event-Based task for Windows OS policy assignment.
- Select **Agent-Initiated-Activation**.
- Click **Next**.

![EBT](/images/ebt2.png) 

---

#### 7. Edit the event configuration as follows:
- Check the box for **Assign Policy**
- From the drop-down select **Base Policy > Windows**
- Click **Next**

![EBT](/images/ebt6.png)


---

#### 8. Specify the following match condition:
- From the left drop-down menu, select **Platform**.
- From the right drop-down menu, enter ```.*Windows.*```
- Click **Next** 

![EBT](/images/ebt7.png) 

---

#### 9. Review Event-Based Task.
- Name: <code>Agent Activation- Windows</code>
- Ensure the Check Box is select next to **Task Enabled**
- Click **Finish**

![EBT](/images/ebt8.png) 

---

#### Under **Administration > Event-Based Tasks** two tasks should appear as below:
![EBT](/images/ebt9.png) 


---
#### Fantastic!! You have successfully have created 2 event-based tasks to automate policy deployment depending on the Platform :cloud: :rocket:
