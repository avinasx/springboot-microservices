# Springboot Microservices Project

## Microservices Architecture

### 1. API Gateway

The API Gateway is designed to provide a simple yet effective solution for routing to APIs and handling cross-cutting concerns such as security, monitoring/metrics, and resiliency. An API Gateway serves as a single entry point for managing, aggregating, and routing API requests. It is a key component in efficiently handling API traffic, ensuring security, and optimizing performance.

### 2. Discovery Server

The service discovery solution is designed to simplify the process of locating and communicating with microservices within distributed application architecture. By utilizing Netflix Eureka, we can effectively manage and coordinate services, making it easier to scale microservices-based applications.

In a microservices architecture, services are distributed across multiple instances and can dynamically scale up or down based on demand. Keeping track of these services and their availability becomes a complex task. Netflix Eureka simplifies this challenge by providing a centralized service registry that allows services to register themselves and query the registry for information about other services.

### 3. Product Service

This microservice, built using Spring Boot and MongoDB, efficiently manages and retrieves product information. It is designed to facilitate the creation and listing of products in an online shopping application.

### 4. Order Service

The Order Service is a microservice designed to place orders online for shopping apps. It communicates synchronously with the Inventory Service, which is distributed across multiple instances with the power of Resilience4j circuit breakers. The Order Service will dynamically discover available Inventory Service instances using the service discovery configuration. It uses inter-process synchronous communication with the Inventory Service to ensure that the available inventory is up-to-date and can fulfill incoming orders.

### 5. Inventory Service

The Inventory Service is a Spring Boot application that provides real-time product availability checks for businesses and e-commerce platforms. This service is designed to help you manage your product inventory efficiently, ensuring that your customers always have access to accurate stock information.

### 6. Notification Service

The Order Service and the Notification Service, which work together to implement an event-driven architecture using Apache Kafka. The Order Service is responsible for processing and generating orders, while the Notification Service consumes events from Kafka to send notifications to users based on the orders.


## Infrastructure Components

### Discovery Server (Netflix Eureka)

1. A service discovery solution that simplifies the process of locating and communicating with microservices in a distributed architecture.

2. Allows services to register themselves, making it easier to scale and manage them dynamically.

3. Provides a centralized registry of services that helps with load balancing and failover.

### Resilience4j Circuit Breakers

1. Implements the circuit breaker pattern to enhance the resilience of the system.

2. Monitors the health of microservices and prevents cascading failures by temporarily breaking the circuit when a service is experiencing issues.

3. Helps in maintaining system stability and preventing the degradation of overall performance.


## Overall Project Structure

1. Each microservice is designed to be independent, with its own database and business logic.

2. Microservices communicate with each other through well-defined APIs, and the Internal Router facilitates this communication.

3. The Discovery Server ensures that microservices can dynamically discover and communicate with each other, providing scalability and flexibility.

4. Resilience4j Circuit Breakers are implemented to handle potential failures gracefully, ensuring the overall system's robustness and availability.


This architecture aims to provide a scalable, resilient, and maintainable solution for the Docquity App, allowing efficient development, deployment, and management of microservices.
