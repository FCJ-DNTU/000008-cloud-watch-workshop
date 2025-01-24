---
title: "CloudWatch Alarms"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

#### CloudWatch Alarms

In this section, we will set up an Alarm for the Error Log Metric that we created in the previous section.

1. Return to the main screen of CloudWatch.

   - Select **Alarms** from the left menu.
   - Choose **All alarms**.
   - Click **Create alarm**.

![5.1](/images/5-cloud-watch-alarm/5.1.png)

2. Select **Select metric**.

![5.2](/images/5-cloud-watch-alarm/5.2.png)

The metrics window appears, under **Custom namespaces**, select **ec2-logs**.

![5.3](/images/5-cloud-watch-alarm/5.3.png)

Next, select **Metrics with no dimensions**, choose **/var/log/messages**, and click **Select metric**.

![5.4](/images/5-cloud-watch-alarm/5.4.png)

3. In the **Specify metric and conditions** section, set **Period** to **1 minute**.

![5.5](/images/5-cloud-watch-alarm/5.5.png)

4. In the **Conditions** section:

   - Threshold type: **Static**.
   - Condition: **Greater** than **10**.

![5.6](/images/5-cloud-watch-alarm/5.6.png)

You will see a dashed line indicating that this is the threshold where the **Alarm** will be triggered => when there are too many errors, something unusual has happened in the application and needs to be checked immediately.

![5.7](/images/5-cloud-watch-alarm/5.7.png)

Then click **Next** to continue.

5. Now, configure the notification as follows:

   - Alarm state trigger: **In alarm**.
   - Choose **Create new topic**.
   - Topic name: `Error_logs_reach_10`.
   - Email to notify: enter your email, here I will enter mine.
   - Click **Create topic**.

![5.8](/images/5-cloud-watch-alarm/5.8.png)

![5.9](/images/5-cloud-watch-alarm/5.9.png)

Click **Next**.

![5.10](/images/5-cloud-watch-alarm/5.10.png)

6. In the final step, enter the alarm name as `PythonApplicationErrorAlarm` and click **Next**.

![5.11](/images/5-cloud-watch-alarm/5.11.png)

7. Review the results and click **Create alarm**.

![5.12](/images/5-cloud-watch-alarm/5.12.png)

![5.13](/images/5-cloud-watch-alarm/5.13.png)

Result:

![5.14](/images/5-cloud-watch-alarm/5.14.png)

8. Log in to Gmail or any email service you use. You will receive an email from **AWS Notification**.

![5.15](/images/5-cloud-watch-alarm/5.15.png)

Click **Confirm subscription**.

![5.16](/images/5-cloud-watch-alarm/5.16.png)

![5.17](/images/5-cloud-watch-alarm/5.17.png)

Okay, now we have completed the alarm setup.
