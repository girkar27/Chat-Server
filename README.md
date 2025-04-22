# ChatHub: A Multiclient Distributed Real-time Room Based Chat Application

Welcome to ChatHub, a powerful distributed chat application designed to support unicast, multicast, and broadcast messaging. This README provides an overview of the architecture and setup instructions for ChatHub.

Live Demo: https://vimeo.com/921546917?share=copy

### Architecture Overview
ChatHub's architecture is meticulously crafted to ensure scalability, reliability, and real-time communication capabilities. Let's explore the key components and their roles:

<img width="987" alt="Distributed Chat Server" src="https://github.com/NihalGajbhiye/ConnectHub-Distributed-Chat-Server/assets/85219483/803d3b0d-33d1-4676-b1af-914a5b48cbbc">

## Components Overview
### Express

Express is a minimalist web framework for Node.js, providing robust features for web and mobile applications. In ChatHub, Express serves as the backbone for handling HTTP requests, routing, and middleware integration.

### Socket.io

Socket.io facilitates real-time bidirectional communication between clients and servers using WebSockets. In ChatHub, Socket.io powers instant messaging capabilities, enabling seamless communication across various devices and platforms.

### Redis

Redis is an in-memory data structure store known for its performance, versatility, and support for various data structures. In ChatHub, Redis serves as a key component for caching, pub/sub messaging, and data synchronization among distributed servers.

- **Subscriber 1:** Subscribes to the `bchat-chats` channel for receiving chat messages.
- **Subscriber 2:** Subscribes to the `bchat-rooms` channel for room-related updates.
- **Subscriber 3:** Subscribes to the `bchat-users` channel for user-related notifications.

### MongoDB

MongoDB is a flexible NoSQL database system used for persistence and data management. In ChatHub, MongoDB stores chat messages, user data, and room configurations, ensuring data consistency and reliability across different deployment scenarios.

### HAProxy

HAProxy is a high-performance load balancer known for its reliability and advanced load balancing algorithms. In ChatHub, HAProxy intelligently distributes incoming client requests across multiple backend servers, enhancing scalability and resource utilization.

## Architecture Details

ChatHub's architecture leverages these components to create a scalable, reliable, and real-time chat application:

### Server Setup

The server setup includes the initialization of Express, Socket.io, and HTTP server instances. Express handles HTTP requests, while Socket.io enables real-time communication between clients and servers.

### Redis Integration

ChatHub integrates Redis for caching, pub/sub messaging, and data synchronization among distributed servers. Redis subscribers listen to specific channels for chat messages, room updates, and user notifications, ensuring seamless communication across the application.

### MongoDB Connection

ChatHub connects to MongoDB for persistence and data management. MongoDB stores chat messages, user data, and room configurations, providing reliable data storage and retrieval capabilities.

### WebSocket Communication

WebSocket communication powered by Socket.io enables real-time bidirectional data exchange between clients and servers. ChatHub utilizes WebSocket connections to deliver instant messages, notifications, and updates to connected clients.

### Load Balancing with HAProxy

HAProxy acts as the load balancer for ChatHub, distributing incoming client requests across multiple backend servers. By evenly distributing traffic, HAProxy optimizes resource utilization, enhances system scalability, and ensures a seamless user experience.



## Setup

### Running the Backend

The backend of ChatHub relies on several essential components for its seamless operation, including `redis`, `mongodb`, and `haproxy`. To streamline the setup process, we've provided a comprehensive `docker-compose.yml` file within the backend directory. Follow these steps to initiate the backend services:

```shell
# Navigate to the backend directory
$ cd chat-app-backend

# Build the chatapp image
$ docker build -t chatapp .

# Start the backend services
$ docker-compose up # Use -d for detached mode

# To stop the services
$ docker-compose down
```

### Running the Frontend Application
The frontend of ChatHub is powered by app.js, housing all the critical business logic for WebSocket establishment and API interactions. Ensure that the backend services are running before proceeding with the frontend server setup:

```shell

# For node modules
$ npm i

# For development server
$ npm start

# Otherwise, build the assets and serve through gserve
$ npm run build && serve ./build
```


### Conclusion
ChatHub represents a sophisticated and scalable solution for real-time communication, offering support for diverse messaging paradigms and distributed deployment environments. With its modular architecture and robust component integration, ChatHub empowers developers to build immersive chat experiences while ensuring optimal performance, reliability, and scalability. Thank you for choosing ChatHub for your real-time communication needs.

Warm regards,
Jai A Girkar



