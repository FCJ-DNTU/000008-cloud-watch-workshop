---
title: "Các bước chuẩn bị"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Các bước chuẩn bị

1. Truy cập vào **AWS Management Console**

   - Tìm **CloudFormation**
   - Chọn **CloudFormation**

![2.1](/images/2-preparatory-steops/2.1.png)

2. Trong giao diện **CloudFormation**

   - Chọn **Create stack**
   - Chọn **With new resources (standard)**

![2.2](/images/2-preparatory-steops/2.2.png)

3. Trong giao diện **Create stack**. Bạn tải file cấu hình [template](https://raw.githubusercontent.com/AWS-First-Cloud-Journey/CloudWatchWorkshop/main/template.yml) về trước và sau đó thực hiện các bước.

   - Trong phần **Prerequisite - Prepare template**, chọn **Choose an existing template**.
   - Tiếp theo chọn **Upload a template file**.
   - Ấn **Choose file** để tải lên file template mới tải về.
   - Ấn **Next**

![2.3](/images/2-preparatory-steops/2.3.png)

4. Tiếp đến là điền các thông tin như sau:

   - Name: `FCJ-CloudWatch-Workshop` (hoặc tên nào đó mà bạn thích, nhưng nên đặt một cái tên dễ gợi nhớ).
   - RegionId: chọn đúng id của region mà bạn đang thực hiện bài lab này, như trong bài này thì mình chọn **us-east-1** (N. Virginia).
   - Parameter còn lại bạn nên giữ nguyên.
   - Ấn **Next**.

![2.4](/images/2-preparatory-steops/2.4.png)

5. Ở trang này thì chúng ta không cần cấu hình gì hết, nên cuộn xuống dưới cùng, tích chọn **I acknowledge that AWS CloudFormation might create IAM resources with custome names**. Sau đó ấn **Next**.

![2.5](/images/2-preparatory-steops/2.5.png)

6. Sau đó thì xác minh lại một lần nữa, cuộn xuống dưới cùng và ấn **Submit** để tạo Stack.

![2.6](/images/2-preparatory-steops/2.6.png)

7. Sau đó thì một stack mới sẽ được tạo, các bạn chờ khoảng 5 phút để hoàn tất việc cài đặt.

![2.7](/images/2-preparatory-steops/2.7.png)

Khi cài đặt xong thì chúng ta có được kết quả như sau.

![2.8](/images/2-preparatory-steops/2.8.png)

Ok như vậy là bước chuẩn bị đã hoàn tất. Trong các bước sau thì chúng ta sẽ tiến hành thực hành trên CloudWatch.
