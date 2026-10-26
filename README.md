# Enterprise-Scale Microservices E-Commerce Engine

A production-grade, distributed full-stack e-commerce catalog system engineered using
**Java 17, Spring Boot 3.x, Spring Cloud, MySQL, and vanilla JavaScript (ES6)**.
This project demonstrates high-availability routing, centralized configuration mesh infrastructure, and low-latency database optimization strategies designed for corporate deployments.

## 🏗️ System Architecture Network Mesh

[ Client Browser UI ]
│
▼ (Port: 8080)
┌───────────────────┐
│   API Gateway     │ <─── [ Central Config Server ] (Port: 8888)
│ (CORS Rules Active)│
└─────────┬─────────┘
│ (Dynamic Lookup Routing Resolution)
▼
┌───────────────────┐
│   Eureka Server   │ (Service Registry Phonebook Hub - Port: 8761)
│ (Health Monitoring)│
└───────────────────┘
│
▼ (Load-Balanced Forwarding Pass)
┌───────────────────┐
│  Product Service  │ (Port: 8081)
└─────────┬─────────┘
│
▼ (Optimized Composite Index Scanning)
┌───────────────────┐
│  MySQL Database   │ (Persistent Storage Tier - Port: 3306)
└───────────────────┘




## 🛠️ Integrated Technology Framework Matrix

| Architectural Layer | Core Integrated Technologies | Operational Port | Production Responsibility Matrix |
| :--- | :--- | :--- | :--- |
| **Frontend UI** | HTML5, CSS3 Grid, JavaScript (Async Fetch ES6) | Local Filesystem | Renders interactive responsive product catalog cards directly via microservice endpoints. |
| **API Entry Middleware** | Spring Cloud Gateway, Reactive Streams | `:8080` | Enforces centralized system ingress, path-matching route patterns, and global CORS policies. |
| **Dynamic Service Hub** | Netflix Eureka Service Registry | `:8761` | Tracks service execution instances and updates routing records dynamically. |
| **Central Property Manager**| Spring Cloud Config Server (Native Profile) | `:8888` | Aggregates and provisions dynamic system property profiles to running nodes. |
| **Domain Microservice** | Spring Boot, Spring Data JPA, Hibernate | `:8081` | Manages operational business workflows and formats transactional database query operations. |
| **Persistent Storage** | Relational Enterprise MySQL Server Engine | `:3306` | Houses persistent records using custom column indexing to ensure low latency. |

## 🚀 Performance Engineering (Database Optimizations)

To ensure sub-millisecond query processing routines across large catalogs, the relational persistence layer implements specialized JPA indexing configurations on the underlying execution tables:
* **Unique SKU Indexing (`idx_product_sku`)**: Prevents duplicate inventory entries and speeds up transactional item lookup cycles.
* **Composite Catalog Indexing (`idx_product_category_price`)**: A compound multi-column index built specifically to optimize high-volume sorting and category filter requests from the user dashboard.

## 💻 Local Development Workspace Setup

### Prerequisites
* Java Development Kit (JDK) 17 or higher
* Apache Maven 3.x
* MySQL Server Instance running locally

### Local Manual Orchestration Sequence
Run these startup commands sequentially in separate isolated execution terminals:

1. **Start the Service Registry:**
   ```bash
   cd discovery-server
   mvn spring-boot:run
   ```
2. **Launch Centralized Configurations Server:**
   ```bash
   cd config-server
   ```
3. **Fire Up the Interceptor API Gateway:**
   ```bash
   cd api-gateway
   mvn spring-boot:run
   ```
4. **Boot Up the Database Connected Business Domain Service:**
   ```bash
   cd product-service
   mvn spring-boot:run
   ```
