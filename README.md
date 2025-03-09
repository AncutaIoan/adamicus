# Social App Backend (Adamicus)

## 📌 Overview
This is the backend for a modern social networking app. It follows a **microservices architecture**, leveraging **Kotlin (Ktor/Spring Boot)** for business logic and **Rust (Actix/Axum)** for high-performance services like graph processing and real-time communication.

---

## 🏗️ Architecture
Each service is designed to be independent, scalable, and optimized for its function.

### **🔹 Kotlin-Based Services** (Business Logic & APIs)
| Service Name       | Responsibility                                      | Tech Stack                        |
|-------------------|-------------------------------------------------|--------------------------------|
| **UserService**     | Authentication, profiles, settings              | Kotlin + Ktor/Spring Boot + PostgreSQL |
| **PostService**     | Creating, liking, and sharing posts              | Kotlin + Ktor + PostgreSQL      |
| **CommentService**  | Handles comments and replies                     | Kotlin + Ktor + PostgreSQL      |
| **NotificationService** | Manages real-time notifications (push, email, in-app) | Kotlin + Ktor + Kafka + Redis  |
| **SearchService**   | Full-text search (users, posts, hashtags)        | Kotlin + Elasticsearch         |

### **🟠 Rust-Based Services** (High-Performance Features)
| Service Name          | Responsibility                                       | Tech Stack                     |
|----------------------|------------------------------------------------|-----------------------------|
| **GraphService**       | Handles relationships (friends, follows, recommendations) | Rust + Actix/Axum + Neo4j     |
| **RecommendationService** | Runs graph algorithms (suggest friends, posts)   | Rust + Actix + Neo4j          |
| **ChatService**        | Real-time messaging (WebSockets, gRPC)             | Rust + Tokio + Redis          |
| **AnalyticsService**   | Collects user interaction data for insights        | Rust + Kafka + ClickHouse     |

---

## 📡 Communication Between Services

- **REST APIs** (Kotlin services) for standard data operations.
- **gRPC** (Rust services) for efficient, high-performance communication.
- **Kafka** for event-driven architecture (user events, notifications, analytics).
- **Redis** for caching and real-time data.

---

## 🛠️ Technologies Used

### **Programming Languages**
- **Kotlin** (Ktor, Spring Boot) → Business logic & APIs
- **Rust** (Actix, Axum, Tokio) → High-performance services

### **Databases & Storage**
- **PostgreSQL** → Structured data (users, posts, comments)
- **Neo4j** → Graph database (friends, follows, recommendations)
- **Redis** → Caching & real-time features
- **ClickHouse** → Analytics & insights
- **Elasticsearch** → Full-text search

### **Messaging & Event Processing**
- **Kafka** → Event-driven architecture (notifications, activity tracking)

### **Infrastructure & Deployment**
- **Docker & Kubernetes** → Containerized deployment
- **Traefik / Kong** → API Gateway
- **Prometheus & Grafana** → Monitoring & logging

---

## 🔥 Setup & Running Locally ( TO BE ADDRESSED )

### **1️⃣ Prerequisites**
Ensure you have the following installed:
- **Docker & Docker Compose**
- **PostgreSQL**
- **Neo4j**
- **Kafka & Zookeeper**
- **Rust & Cargo**
- **Kotlin & Gradle**


---

## 🚀 API Routes

### **UserService** (Kotlin, REST)
| Method | Endpoint              | Description              |
|--------|----------------------|--------------------------|
| GET    | `/users/{id}`         | Get user profile        |
| POST   | `/users/register`     | Register a new user     |
| PUT    | `/users/{id}`         | Update user info        |

### **PostService** (Kotlin, REST & WebSockets)
| Method | Endpoint              | Description                 |
|--------|----------------------|-----------------------------|
| GET    | `/posts/{id}`         | Get post by ID             |
| POST   | `/posts`              | Create a new post          |
| GET    | `/posts/live` (WS)    | Live updates for posts     |

### **GraphService** (Rust, gRPC)
| gRPC Method | Request         | Response                   |
|------------|----------------|---------------------------|
| `GetFriends` | User ID        | List of friend user IDs   |
| `RecommendPosts` | User ID    | List of recommended posts |

---

## 🔄 Future Improvements
✅ Add support for GraphQL. (~MAYBE)
✅ Implement machine learning-based recommendations. (~MAYBE)
✅ Improve API security (OAuth, JWT). (~MAYBE)

---

## 🤝 Contributing
Feel free to open issues and pull requests to contribute to the project!

---

## 📄 License
MIT License © 2025 Your Name/Company

