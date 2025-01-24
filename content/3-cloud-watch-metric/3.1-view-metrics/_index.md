---
title: "Viewing Metrics"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

#### Viewing Metrics

First, we will practice viewing metrics.

1. Access **AWS Management Console**
   - Search for **CloudWatch**
   - Select **CloudWatch**

![3.1.1](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.1.png)

2. In the **CloudWatch** interface
   - Expand the **Metrics** section in the left menu.
   - Select **All metrics**.

![3.1.2](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.2.png)

3. In the metrics dashboard, enter `EC2` in the search bar.

![3.1.3](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.3.png)

4. Once the results appear, select **EC2 > Per-Instance Metrics**.

![3.1.4](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.4.png)

![3.1.5](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.5.png)

5. In the search bar, type `CPUUtilization` and search.

![3.1.6](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.6.png)

By default, the search is performed by **Metric name**.

![3.1.7](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.7.png)

6. Add two out of the five instances created by the CloudFormation stack to observe their `CPUUtilization` metrics.

Scroll down to view the data.

From the graph, we can conclude:

- Both instances started operating around **2:40 AM**, which is also when they had the highest activity.
- By **3:30 AM**, both instances seem to have completed their tasks.

![3.1.8](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.8.png)

7. Viewing additional metrics for a single instance
   - Deselect the line for **Instance B**.
   - Remove the **CPUUtilization** filter.
   - In the search bar, enter `EBSWriteBytes` and search.

![3.1.9](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.9.png)

![3.1.10](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.10.png)

8. Scroll down and select **Instance A**.

From this chart, we observe:

- Initially, there was a high volume of read/write operations to **EBS**, indicating that the instance was processing data.
- **CPUUtilization** and **EBSWriteBytes** follow a similar pattern, except at certain points where they diverge.
- This suggests that the application interacts with **EBS** mainly during startup but performs other tasks afterward.

![3.1.11](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.11.png)

You can hide one of the metrics to analyze the data more clearly.

![3.1.12](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.12.png)

However, we will take a better approach in the next section by customizing the charts for improved visualization.

## Working with Charts

In the previous step, our chart was difficult to interpret because both `CPUUtilization` and `EBSWriteBytes` were plotted on the same **Y-axis**. Now, we will separate them and add markers for better visualization.

1. Adjusting the Y-axis
   - Go to the **Graphed metrics** tab.
   - Locate **EBSWriteBytes**, then under the **Y-axis** column, select **>**.
   - The chart should now appear more readable.

![3.1.13](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.13.png)

2. Adding a horizontal annotation (threshold marker)
   - Go to the **Options** tab.
   - Click **Add horizontal annotation**.

![3.1.14](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.14.png)

3. Enter annotation details:
   - **Label:** `5% Mark`
   - **Value:** `5`

This adds a **dashed line** on the chart, labeled accordingly.

![3.1.15](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.15.png)

4. Adding a vertical annotation (event marker)
   - Create a **Vertical annotation** labeled `Job start`.
   - A **dashed vertical line** appears on the chart.

![3.1.16](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.16.png)

By default, the **Job start** marker is set at **2:16 AM**, but this is incorrect. We need to adjust it.

5. Adjusting the vertical annotation time:
   - Hover over the **Job start** marker.
   - The job actually started around **2:40 AM**.

![3.1.17](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.17.png)

- Change the **Date/Time** for `Job start` to **2:40 AM**.
- Click **Apply** to save changes.

![3.1.18](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.18.png)

The `Job start` marker has now been repositioned.

![3.1.19](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.19.png)

That concludes our hands-on work with charts.

In the next section, we will focus on **working with metric expressions**. You can remove the markers before proceeding to the next step.
