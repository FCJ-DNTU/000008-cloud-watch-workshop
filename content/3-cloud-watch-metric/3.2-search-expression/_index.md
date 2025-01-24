---
title: "Search expressions"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

#### Search Expressions

In the previous section, we manually viewed metrics, but this method has limitations and requires multiple interactions with different metrics. In this section, we can perform this more efficiently using Search Expressions.

1. Remove all information from the old graph by clicking **X** or **Clear graph**.

![3.2.1](/images/3-cloud-watch-metric/3.2-search-expression/3.2.1.png)

2. Return to the **Browse** tab

   - Remove the **EBSWriteBytes** filter.
   - Add **CPUUtilization**.
   - Click **Graph search**.

![3.2.2](/images/3-cloud-watch-metric/3.2-search-expression/3.2.2.png)

![3.2.3](/images/3-cloud-watch-metric/3.2-search-expression/3.2.3.png)

3. Go back to the **Graphed metrics** tab, where a new search expression has appeared in the **Details** column.

![3.2.4](/images/3-cloud-watch-metric/3.2-search-expression/3.2.4.png)

4. Enter a new expression as shown below. This expression searches in a different Namespace outside EC2.

Then, click **Apply** to apply the changes.

![3.2.5](/images/3-cloud-watch-metric/3.2-search-expression/3.2.5.png)

In the upper-right corner

- Open the **Line** dropdown.
- Select **Stacked area**.

![3.2.6](/images/3-cloud-watch-metric/3.2-search-expression/3.2.6.png)

Now, the graph is easier to read.

![3.2.7](/images/3-cloud-watch-metric/3.2-search-expression/3.2.7.png)

5. Search for the average memory usage percentage (Disk Used Percent)

```
SEARCH("disk_used_percent", 'Average', 300)
```

![3.2.8](/images/3-cloud-watch-metric/3.2-search-expression/3.2.8.png)

![3.2.9](/images/3-cloud-watch-metric/3.2-search-expression/3.2.9.png)

6. Search using the keyword "used"

```
SEARCH("used", 'Average', 300)
```

![3.2.10](/images/3-cloud-watch-metric/3.2-search-expression/3.2.10.png)

The results have changed slightly.

![3.2.11](/images/3-cloud-watch-metric/3.2-search-expression/3.2.11.png)

Okay, so we have completed the basic search operations in CloudWatch Console. In the next section, we will perform simple calculations.
