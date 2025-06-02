---
title: "Buổi  - Truyền thông"
date: "2025-12-5"
updated: "2025-12-5"
categories:
  - "sveltekit"
  - "markdown"
coverWidth: 16
coverHeight: 9
excerpt: Check out how heading links work with this starter in this post.
---

#  Tìm hiểu RabbitMQ – Dịch vụ truyền thông điệp trong hệ thống phân tán

## 1. Giới thiệu

Trong hệ thống phân tán, việc giao tiếp giữa các tiến trình không thể thực hiện trực tiếp bằng lời gọi hàm như trong hệ thống đơn. Ta cần một **cơ chế truyền thông điệp bất đồng bộ**.  
**RabbitMQ** là một trong những phần mềm **Message Broker** phổ biến, giúp các thành phần trong hệ thống giao tiếp với nhau một cách **tách biệt, bất đồng bộ và an toàn**.

---

## 2. RabbitMQ là gì?

- RabbitMQ là một hệ thống **hàng đợi thông điệp (message queue)** mã nguồn mở.
- Hoạt động theo giao thức **AMQP (Advanced Message Queuing Protocol)**.
- Đóng vai trò trung gian nhận, lưu trữ và phân phối các thông điệp giữa **Producer** và **Consumer**.

---

## 3. Kiến trúc hoạt động

```text
Producer --> Exchange --> Queue --> Consumer
````

### Các thành phần chính:

* **Producer**: gửi thông điệp (message).
* **Exchange**: định tuyến thông điệp đến đúng hàng đợi (queue).
* **Queue**: lưu trữ thông điệp chờ xử lý.
* **Consumer**: nhận và xử lý thông điệp từ queue.

### Các loại `Exchange`:

| Loại Exchange | Chức năng                                      |
| ------------- | ---------------------------------------------- |
| **Direct**    | Gửi đến queue có `routing key` khớp chính xác. |
| **Fanout**    | Gửi đến tất cả các queue liên kết.             |
| **Topic**     | Gửi dựa trên pattern, ví dụ: `log.*`.          |
| **Headers**   | Dựa trên các cặp key–value trong header.       |

---

## 4. Ưu điểm và chức năng

* Hỗ trợ **giao tiếp bất đồng bộ** giữa các tiến trình.
* **Đảm bảo độ tin cậy**: có cơ chế xác nhận, lưu trữ bền vững.
* Dễ dàng **mở rộng theo chiều ngang**.
* Hỗ trợ nhiều **ngôn ngữ lập trình** như Python, Java, Go, v.v.
* Có **giao diện quản trị web** tiện lợi (port 15672).

---

## 5. Cài đặt RabbitMQ (bằng Docker)

Cài đặt RabbitMQ nhanh qua Docker:

```bash
docker run -d --hostname my-rabbit --name rabbitmq \
  -p 5672:5672 -p 15672:15672 \
  rabbitmq:3-management
```

* Truy cập: [http://localhost:15672](http://localhost:15672)
* Tài khoản mặc định:

  * Username: `guest`
  * Password: `guest`

---

## 6. Ứng dụng thực tế

RabbitMQ được sử dụng trong:

* **Xử lý email hàng loạt**.
* Giao tiếp giữa các **microservices**.
* Hệ thống **event-driven** với mô hình **publish/subscribe**.
* Tích hợp với **Celery** để xử lý tác vụ nền trong Python.

---

## 7. Tổng kết

RabbitMQ là một giải pháp hiệu quả, ổn định và dễ sử dụng trong việc **truyền thông điệp giữa các tiến trình phân tán**. Nó đặc biệt phù hợp trong kiến trúc microservices, các hệ thống cần xử lý bất đồng bộ hoặc có độ trễ cao.

> ✅ Với RabbitMQ, việc xây dựng các hệ thống phân tán trở nên đơn giản, có thể mở rộng và dễ bảo trì hơn.

---

*Báo cáo thực hiện cho: Bài tập 1 – Phần 5
Học phần: Ứng dụng phân tán – Đại học Phenikaa*

```

---

Nếu bạn muốn mình tạo một **file `.md` để tải về** hoặc hỗ trợ làm tiếp bài 2 (code ví dụ), mình sẵn sàng hỗ trợ ngay!
```
