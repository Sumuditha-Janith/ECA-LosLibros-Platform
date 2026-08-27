# 🛠️ LosLibros - Platform Infrastructure Module

[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.0-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-2025.x-blue.svg)](https://spring.io/projects/spring-cloud)

The `platform/` directory contains all Spring Cloud infrastructure components that power the LosLibros microservice ecosystem.

---

## 📦 Submodules

| Module | Service Name | Default Port | Description |
| :--- | :--- | :--- | :--- |
| **[`config-server`](./config-server/README.md)** | `Config-Server` | `9000` | Centralized Git and native classpath configuration provider. |
| **[`service-registry`](./service-registry/README.md)** | `service-registry` | `9001` | Spring Cloud Netflix Eureka service registration & discovery server. |
| **[`api-gateway`](./api-gateway/README.md)** | `api-gateway` | `7000` | Reactive Spring Cloud Gateway reverse proxy, load balancer, and CORS handler. |

---

## 🚀 Startup Order

Always start the platform modules in this exact order:

1. **Config Server** (Port `9000`):
   ```bash
   cd config-server && ./mvnw spring-boot:run
   ```
2. **Service Registry** (Port `9001`):
   ```bash
   cd ../service-registry && ./mvnw spring-boot:run
   ```
3. **API Gateway** (Port `7000`):
   ```bash
   cd ../api-gateway && ./mvnw spring-boot:run
   ```

---

## ⚡ PM2 Process Management

For production or background execution, an `ecosystem.config.js` file is provided:

```bash
# Build all platform JARs
mvn clean package -DskipTests

# Start all platform components with PM2
pm2 start ecosystem.config.js
```

---

## 👤 Student Information

- **Student Name:** E. Sumuditha Janith
- **Student Number:** 241711016
- **GCP Project ID:** eca-gdse-71-loslibros
- **Slack Handle:** https://ijse-eca-hdse-71-72.slack.com/team/U0BF55V8V0W

