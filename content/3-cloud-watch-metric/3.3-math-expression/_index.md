---
title: "Math expressions"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

#### Mathematical Expressions

Continuing, in this section, we will perform basic mathematical expressions.

1. First, clear the previous search expression.

![3.3.1](/images/3-cloud-watch-metric/3.3-math-expression/3.3.1.png)

2. Go back to the **Browse** tab.

   - Click **Graph search** to restore the graph from the previous step.

![3.3.2](/images/3-cloud-watch-metric/3.3-math-expression/3.3.2.png)

3. Next, open the **Add math** section in the upper-right corner, below the graph.

   - Expand **Filter**.
   - Select **Top 10 by sum**.

![3.3.3](/images/3-cloud-watch-metric/3.3-math-expression/3.3.3.png)

![3.3.4](/images/3-cloud-watch-metric/3.3-math-expression/3.3.4.png)

4. Now, we will reorder the graph based on the first search expression using the expression below.

```
SORT(e1, SUM, DEC, 3)
```

![3.3.5](/images/3-cloud-watch-metric/3.3-math-expression/3.3.5.png)

![3.3.6](/images/3-cloud-watch-metric/3.3-math-expression/3.3.6.png)

That's it! In this section, we kept it simple. Let's continue practicing in the next part.
