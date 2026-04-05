# ECommerceMicroservices

A relatively comprehensive e-commerce project built with a microservices architecture on .NET Core.  
The project includes API gateway routing, centralized identity management, payment integration, real-time chat, and asynchronous service communication.

## Overview

This repository is a backend-focused e-commerce system designed to explore real-world microservice patterns and common distributed application concerns.

It brings together multiple services behind an Ocelot API Gateway, uses Duende IdentityServer for authentication and authorization, integrates Iyzico for payment processing, and supports real-time customer communication with SignalR.

The project was built to practice and demonstrate how different backend components can work together in a modular and scalable architecture.

## Features

- Microservices-based architecture
- Ocelot API Gateway for routing and aggregation
- Duende IdentityServer for centralized authentication and authorization
- Iyzico payment integration
- SignalR-based real-time chat between customer and admin
- Order confirmation email flow
- Service separation for core e-commerce domains
- Message bus-based communication for asynchronous workflows

## Project Structure

The solution is organized into multiple projects and services:

- `Inveon.Gateway.Solution`  
  API Gateway layer built with Ocelot

- `Inveon.Services.Identity`  
  Identity and authentication service using Duende IdentityServer

- `Inveon.Services.ProductAPI`  
  Product-related operations

- `Inveon.Services.ShoppingCartAPI`  
  Shopping cart management

- `Inveon.Services.OrderAPI`  
  Order creation and processing

- `Inveon.Services.CouponAPI`  
  Coupon and discount-related operations

- `Inveon.Services.Email`  
  Email sending and notification workflows

- `Inveon.MessageBus`  
  Shared messaging and asynchronous communication layer

- `Inveon.Web`  
  Web application / presentation layer

## Architecture

The system follows a microservice-oriented design where each service is responsible for a specific business capability.

A typical flow looks like this:

1. The client sends requests through the API Gateway.
2. Identity and access control are handled by the Identity service.
3. Product, cart, coupon, and order operations are processed by their corresponding services.
4. Payment operations are integrated with Iyzico.
5. Real-time communication is handled through SignalR.
6. Background or cross-service workflows are coordinated through the message bus.
7. Email notifications are triggered for events such as order confirmation.

This separation helps keep responsibilities clear and makes the system easier to evolve and maintain.

## Technologies

- .NET Core / ASP.NET Core
- Ocelot API Gateway
- Duende IdentityServer
- SignalR
- Iyzico Payment API
- Message bus-based communication
- Mail-based notification flow

## Main Capabilities

### Authentication and Authorization
The project uses Duende IdentityServer to centralize authentication and provide a more structured security model across services.

### Payment Integration
Payment operations are integrated with Iyzico to simulate a real e-commerce checkout flow.

### Real-Time Chat
SignalR is used to provide a live chat feature between customer and admin.

### Gateway-Based Access
Ocelot acts as the single entry point for routing incoming requests to the appropriate downstream services.

### Async Communication
Some workflows are decoupled through the messaging layer, making the overall architecture closer to production-style microservice systems.

## Getting Started

### Prerequisites

Before running the project, make sure you have:

- .NET SDK installed
- A database configured for the services
- Required configuration values for:
  - Identity service
  - Iyzico payment integration
  - Email settings
  - Gateway and service URLs
  - Message bus connection settings

### Run

Clone the repository:

```bash
git clone https://github.com/sbrsn97/ECommerceMicroservices.git
cd ECommerceMicroservices
```

Restore dependencies:

```bash
dotnet restore
```

Build the solution:

```bash
dotnet build
```

Run the required services and the gateway according to your local configuration.

## Notes

This project was developed as a hands-on microservices practice project and includes several common patterns used in distributed backend systems, such as gateway-based routing, centralized identity, asynchronous communication, external payment integration, and real-time messaging.

## Repository Purpose

This repository is mainly intended to showcase:

- backend engineering skills
- microservice design concepts
- service decomposition
- authentication and identity management
- integration with external systems
- real-time communication patterns in a distributed application
