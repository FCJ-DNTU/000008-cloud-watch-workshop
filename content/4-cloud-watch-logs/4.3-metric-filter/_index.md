---
title: "CloudWatch Metric Filter"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

#### CloudWatch Metric Filter

1. Return to the main screen of **CloudWatch**

   - Select **Log groups**
   - Search for `/ec2`.
   - Select **/ec2/linux/var/log/messages**

![4.3.1](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.1.png)

2. In the interface of **/ec2/linux/var/log/messages**

   - Click on **Actions**.
   - Click **Create metric filter**.

![4.3.2](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.2.png)

3. In the **Define Pattern** section, enter the following information:

   - Filter pattern: select **ERROR** from the dropdown.
   - Test pattern: select any instance, but it’s recommended to choose the instance where we created processes in the previous two steps.

![4.3.3](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.3.png)

4. Click **Test pattern** to check if the filter works properly.

![4.3.4](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.4.png)

5. In the **Create filter name** section of **Assign metric**, enter `PythonAppErrors`.

![4.3.5](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.5.png)

6. In the **Metric details** section, enter the following information:

   - Metric namespace: `ec2-logs`.
   - Metric name: `/var/log/messages - ERROR`.
   - Metric value: **1**.
   - Default value: **0**.
   - Unit: select **Count** from the dropdown.
   - Click **Next**.

![4.3.6](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.6.png)

7. After reviewing, click **Create metric filter**.

![4.3.7](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.7.png)

![4.3.8](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.8.png)

8. Go back to Metrics > All metrics.

   - Search for the keywords `/var/log/messages` and `ERROR`.
   - Select **ec2-logs > Metrics with no dimensions**.

![4.3.9](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.9.png)

![4.3.10](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.10.png)

Now we have a metric that retrieves ERROR logs from the application. In the next step, we will set up an alarm for this metric.
