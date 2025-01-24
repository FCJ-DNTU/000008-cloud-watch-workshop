---
title: "Preparatory steps"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Preparation Steps

1. Access the **AWS Management Console**:

   - Search for **CloudFormation**.
   - Select **CloudFormation**.

![2.1](/images/2-preparatory-steops/2.1.png)

2. In the **CloudFormation** interface:

   - Select **Create stack**.
   - Choose **With new resources (standard)**.

![2.2](/images/2-preparatory-steops/2.2.png)

3. In the **Create stack** interface. First, download the [template](https://raw.githubusercontent.com/AWS-First-Cloud-Journey/CloudWatchWorkshop/main/template.yml) file, and then follow these steps:

   - In the **Prerequisite - Prepare template** section, choose **Choose an existing template**.
   - Then, select **Upload a template file**.
   - Click **Choose file** to upload the template file you just downloaded.
   - Click **Next**.

![2.3](/images/2-preparatory-steops/2.3.png)

4. Next, fill in the following information:

   - Name: `FCJ-CloudWatch-Workshop` (or any name you prefer, but it’s a good idea to choose a memorable name).
   - RegionId: select the region ID where you are performing the lab, for this lab, I chose **us-east-1** (N. Virginia).
   - Leave the remaining parameters as is.
   - Click **Next**.

![2.4](/images/2-preparatory-steops/2.4.png)

5. On this page, no configuration is needed, so scroll down to the bottom, check **I acknowledge that AWS CloudFormation might create IAM resources with custom names**, and then click **Next**.

![2.5](/images/2-preparatory-steops/2.5.png)

6. Verify everything once more, scroll to the bottom, and click **Submit** to create the stack.

![2.6](/images/2-preparatory-steops/2.6.png)

7. A new stack will be created. Wait for about 5 minutes for the installation to complete.

![2.7](/images/2-preparatory-steops/2.7.png)

When the installation is finished, you should see the following result:

![2.8](/images/2-preparatory-steops/2.8.png)

The preparation step is now complete. In the following steps, we will proceed with hands-on practice in CloudWatch.
