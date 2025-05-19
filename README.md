#📬 Notification Service (Java Spring Boot)

This is a simple Notification Service built with Java and Spring Boot. It allows sending and retrieving notifications of types: **EMAIL**, **SMS**, and **IN_APP**.

---

## 🚀 Features

- ✅ Send notifications via REST API
- ✅ Retrieve user notifications
- ✅ Supports multiple types: EMAIL, SMS, IN_APP
- ✅ Asynchronous processing with RabbitMQ (optional bonus)
- ✅ In-memory H2 database
- ✅ Simulated notification delivery

---

## 🛠 Tech Stack

- Java 17+
- Spring Boot
- Spring Web, JPA
- H2 Database
- RabbitMQ (optional, for queue-based delivery)
- Maven

---

## 📦 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/notification-service.git
cd notification-service
````

Or download as a ZIP and extract.

### 2. Start RabbitMQ (Optional, Bonus Feature)

You can skip this if you're not using queuing.

Using Docker:

```bash
docker run -d --hostname my-rabbit --name rabbitmq \
  -p 5672:5672 -p 15672:15672 rabbitmq:3-management
```

Visit the RabbitMQ UI at [http://localhost:15672](http://localhost:15672)
**Username**: guest | **Password**: guest

### 3. Run the Application

```bash
mvn spring-boot:run
```

The server starts at `http://localhost:8080`

---

## 🧪 API Endpoints

### ➤ Send Notification

* **POST** `/notifications`
* **Request Body:**

```json
{
  "userId": 1,
  "type": "EMAIL",
  "content": "Welcome to our service!"
}
```

---

### ➤ Get User Notifications

* **GET** `/notifications/user/{userId}`

Returns all notifications sent to a user.

---

## 📂 Example cURL Requests

**Send Notification:**

```bash
curl -X POST http://localhost:8080/notifications \
     -H "Content-Type: application/json" \
     -d '{"userId":1,"type":"SMS","content":"Your OTP is 123456"}'
```

**Get Notifications:**

```bash
curl http://localhost:8080/notifications/user/1
```

---

## 📝 Assumptions

* Users are pre-seeded or created separately.
* Delivery is simulated via console logs.
* RabbitMQ usage is optional (bonus feature).

---

## 📄 License

This project is open-source and available under the MIT License.

---

