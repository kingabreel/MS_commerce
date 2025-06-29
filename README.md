# Microservices Architecture with Spring Cloud

This project demonstrates a modular microservices architecture built using Spring Boot and Spring Cloud. It showcases service registration and discovery, centralized API Gateway routing, and modular service communication in a distributed system.

## Project Structure

```
microservices-project/
│
├── api-gateway/ # Spring Cloud Gateway
├── products_api/ # Product management service
├── products_requester/ # Service that consumes product API
├── service-discovery/ # Eureka server for service registry
└── README.md # Project overview
```


## Objectives

- Implement service discovery and registration using Eureka.
- Route and secure microservice requests through Spring Cloud Gateway.
- Demonstrate inter-service communication in a microservices architecture.
- Showcase a simple API flow from request to response across multiple services.

## Technologies

- **Java 17+**
- **Spring Boot 3**
- **Spring Cloud 2023.x**
- **Spring Cloud Gateway**
- **Spring Web**
- **Eureka (Service Discovery)**
- **H2 In-Memory Database**
- **Maven**

## Getting Started

### Prerequisites

- Java 17+
- Maven 3.8+
- Docker

### Running Locally

Start the services in the following order:

1. **Eureka Server (service-discovery)**  
   Runs on `http://localhost:8761` and allows service registration.

2. **API Gateway (api-gateway)**  
   Listens on `http://localhost:8765` and forwards requests to services via Eureka.

3. **Products API (products_api)**  
   Exposes REST endpoints for managing products.

4. **Products Requester (products_requester)**  
   Consumes endpoints from `products_api` via gateway routing.

### Example Requests

- Access H2 Console:  
  `http://localhost:8100/h2-console`

- List products via gateway:  
  `GET http://localhost:8765/products-api/v1/products`

## Notes

- Service names are registered in Eureka and referenced by the Gateway via `lb://{service-id}` URIs.
- Gateway route paths should strip the prefix to match service endpoints.

## Next Steps

- Add centralized logging and monitoring
- Add spring security to make the APIs reject requests with an origin different from the gateway

