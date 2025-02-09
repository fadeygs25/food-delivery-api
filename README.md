# Food Delivery App

A microservices-based food delivery application built with **ASP.NET Core**, **Docker**, and **Kubernetes**. This project follows Clean Architecture and is designed to be scalable and maintainable.

---

## Table of Contents

- [Food Delivery App](#food-delivery-app)
  - [Table of Contents](#table-of-contents)
  - [Technologies](#technologies)
  - [Project Structure](#project-structure)
  - [Setup Instructions](#setup-instructions)
    - [Prerequisites](#prerequisites)
    - [Running with Docker Compose](#running-with-docker-compose)
    - [Running with Kubernetes](#running-with-kubernetes)
  - [API Documentation](#api-documentation)
  - [Contributing](#contributing)
  - [License](#license)
  - [Contact](#contact)

---

## Technologies

- **Microservices**: ASP.NET Core
- **Databases**:
  - PostgreSQL (UserService, OrderService)
  - MongoDB (RestaurantService)
  - Redis (DeliveryService)
- **Message Brokers**: Kafka, RabbitMQ
- **API Gateway**: Ocelot
- **Authentication**: Duende IdentityServer
- **Deployment**: Docker, Kubernetes
- **CI/CD**: GitHub Actions

---

## Project Structure

```
📦 FoodDeliveryApp
┣ 📁 src
┃ ┣ 📁 Services
┃ ┃ ┣ 📁 UserService             # User management (ASP.NET Core + PostgreSQL)
┃ ┃ ┣ 📁 RestaurantService       # Restaurant management (ASP.NET Core + MongoDB)
┃ ┃ ┣ 📁 OrderService            # Order management (ASP.NET Core + PostgreSQL)
┃ ┃ ┣ 📁 DeliveryService         # Delivery management (ASP.NET Core + Redis)
┃ ┃ ┣ 📁 PaymentService          # Payment processing (ASP.NET Core + Stripe)
┃ ┃ ┗ 📁 NotificationService     # Notifications (ASP.NET Core + Kafka/SQS)
┃ ┣ 📁 Shared                    # Shared libraries
┃ ┣ 📁 API Gateways              # API Gateway (Ocelot)
┃ ┣ 📁 Identity                  # Authentication & Authorization
┃ ┗ 📁 EventBus                  # Event-driven communication (Kafka/RabbitMQ)
┣ 📁 deployments
┃ ┣ 📁 k8s                      # Kubernetes manifests
┃ ┣ 📁 docker                   # Docker Compose files
┃ ┗ 📁 terraform                # Infrastructure as Code (IaC)
┣ 📁 tests                      # End-to-End and Load Testing
┣ 📁 docs                       # Project documentation
┣ 📁 .github                    # CI/CD pipelines (GitHub Actions)
┣ 📜 docker-compose.yml         # Docker Compose file
┣ 📜 README.md                  # Project guide
┗ 📜 .gitignore                 # Files to ignore in Git
```

---

## Setup Instructions

### Prerequisites

Before running the project, ensure you have the following installed:

- [.NET 5.0 SDK](https://dotnet.microsoft.com/download)
- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Kubernetes](https://kubernetes.io/docs/setup/) (optional)
- [PostgreSQL](https://www.postgresql.org/download/) (optional)
- [MongoDB](https://www.mongodb.com/try/download/community) (optional)
- [Redis](https://redis.io/download) (optional)

---

### Running with Docker Compose

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/FoodDeliveryApp.git
   cd FoodDeliveryApp
   ```

2. Build and run the project using Docker Compose:
   ```bash
   docker-compose up --build
   ```

3. Access the services:
   - API Gateway: `http://localhost:5000`
   - User Service: `http://localhost:5001`
   - Restaurant Service: `http://localhost:5002`
   - Order Service: `http://localhost:5003`
   - Delivery Service: `http://localhost:5004`
   - Payment Service: `http://localhost:5005`
   - Notification Service: `http://localhost:5006`

---

### Running with Kubernetes

1. Ensure Kubernetes is enabled in Docker Desktop or set up a Kubernetes cluster.

2. Apply the Kubernetes manifests:
   ```bash
   kubectl apply -f deployments/k8s/
   ```

3. Access the services using the exposed endpoints.

---

## API Documentation

API documentation is available using **Swagger**. After running the project, access the Swagger UI at:

- API Gateway: `http://localhost:5000/swagger`
- Individual Services: `http://localhost:<port>/swagger`

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeatureName`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact

For any questions or feedback, please contact:

- **Your Name**
- **Email**: your.email@example.com
- **GitHub**: [your-username](https://github.com/your-username)

---