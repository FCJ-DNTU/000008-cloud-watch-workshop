---
title: "Giới thiệu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Tổng quan

Trong bài lab này chúng ta sẽ thực hành với Amazon CloudWatch, thông qua các thao tác sau:

- Thực hành thao tác với các **Metrics** được gửi từ các ứng dụng mẫu đang chạy trong các EC2 Instances đã được setup từ trước đó.
- Xem các **Logs** cũng được gửi từ chính các ứng dụng chạy trong các EC2 Instances đó. Sau đó là tạo các **Metrics** từ **Logs**.
- Tạo Alarm từ các **Metrics**.
- Và cuối cùng là thực hiện việc thêm các Custom Metrics, Alarm vào trong CloudWatch Dashboard để thiện quan sát hệ thống.

Đây là bài workshop phù hợp cho những bạn / anh / chị có định hướng làm về System để bắt đầu sử dụng dịch vụ CloudWatch để quan sát một hệ thống đơn giản từ đó đưa ra được góc nhìn trực quan hơn về System Monitoring / Observation.
