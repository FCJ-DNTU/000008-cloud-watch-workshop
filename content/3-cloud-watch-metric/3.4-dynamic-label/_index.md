---
title: "Dynamic Labels"
weight: 4
chapter: false
pre: " <b> 3.4 </b> "
---

#### Dynamic Labels

Until now, you may have noticed that the labels in the graph legend have never been updated. While you can manually edit them, doing so for multiple metrics is not ideal. In this section, we will explore how to automatically update labels without manual changes.

1. Clear the previous expressions.

![3.4.1](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.1.png)

2. Remove all **Filters** and click **All** to return to the namespaces.

![3.4.2](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.2.png)

3. Navigate to the **CWAgent** namespace.

![3.4.3](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.3.png)

4. Select the following dimensions: **ImageId, InstanceId, InstanceType, exe, process_name**.

![3.4.4](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.4.png)

![3.4.5](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.5.png)

5. In the search bar, enter the following:

   - `exe=cloudwatch`
   - `MetricName=procstat_memory_rss` (specifying the exact metric name).

![3.4.6](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.6.png)

6. Click **Graph search** to display the graph.

![3.4.7](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.7.png)

7. Switch to the **Graphed metrics** tab.

   - Expand **Add dynamic label**.
   - Expand **All labels**.
   - Select **PROP('Dim.DimName')**.

![3.4.8](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.8.png)

You will see that the graph labels have been updated.

![3.4.9](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.9.png)

8. Modify the label expression as follows:

```
${PROP('Dim.exe')} - ${PROP('Dim.InstanceId')} - ${PROP('MetricName')}
```

![3.4.10](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.10.png)

The labels are now displayed in the updated format.

![3.4.11](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.11.png)
