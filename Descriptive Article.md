# Difference between SOAP and REST API 
This document discusses two widely used methods of designing API - SOAP and REST.

# SOAP
**SOAP** stands for Simple Object Access Protocol. It is a secure protocol which used HTTP as a medium for transfer of messages between systems or applications.<br> 
The data transfer is secured by inbuilt security and WS security. It uses XML as a data format and can be relatively slower in processing when compared to REST.<br> 
It supports both state and stateless data transfer.<br>
SOAP protocol defines 4 elements of designing an API:
- **Envelope**: Defines the structure of the XML
- **Encoding**: Defines the usage of data
- **Request**: Contains the request code to the server
- **Response**: Contains the response from the server

# Security
SOAP has Web Standards Security along with in-built security utilities. The protocol is highly secure and robust.

# Usage
Its secure nature is ideal for use in payment gateways, financial transactions, and data sensitive enterprise applications.

# Advantages of SOAP
- A highly secure and robust protocol
- Platform and language independent
- Carries in-built error handling capabilities

# Drawbacks of SOAP
- Heavy weight and slow in processing speed
- Complicated and less flexible when compared to REST
- API caching is not supported

# REST API
**REST** stands for Representational State Transfer. This is not a protocol but an architecture that uses HTTP methods like GET, PUT, POST, and DELETE to perform CRUD operations.<br> 
It runs on light weight stateless architecture that uses XML, JSON, YAML as a data format. 
REST is built on six constraints upon which it is built:
- Caching
- Uniform interface
- Stateless
- Layered System
- Code on demand
- Client-server diffrentiation

# Security
REST API uses **OAUTH**, **Basic Authentication**, **Bearer Authentication**, and **API keys** as authorization and authentication methods.
# Usage
It’s lightweight, scalable, and flexible nature is ideal for use in streaming services, social media applications, micro-services, and IoT devices.

# Advantages of REST API
- **Scalable**: Since the client and the server are diVerentiated, scalability can be achieved with increasing requests for information.
- **Lightweight**: REST API supports XML, JSON, YAML, or any plain text as data formats making it lightweight in processing and thereby faster.
- **Caches API**: The request results are cached so response for similar requests are sent faster.
- **Stateless**: REST APIs do not store the state of the client treating each request as hereby treating each request as independent of the previous request.
# Drawbacks of REST API
- Less secure compared to SOAP API, not recommended for use in banking, and financial transactions.
- Versioning can be a double edged sword, while being great tool to diffrentiate changes, too many versions can lead to issues of compatibility and clutter.

# Sample REST API Request 
```
{
  "customer_id": "CUST7890",
  "items": [
    {
      "product_id": "PIZZA123",
      "quantity": 2
    }
  ],
  "payment_method": "card"
}
```
# Sample REST API Response
```
{
  "order_id": "ORD12345",
  "status": "confirmed",
  "estimated_delivery": "2025-08-20"
}
```
# Glossary 
- **Stateful**: In a stateful SOAP API, the servers maintain a record of the previous interactions with a specific client. This means that each new request from that client can draw information or context from the previous requests within the same session or transaction.<br>
- **Stateless**: In a stateless API, especially in REST, the servers don't maintain a record of the previous interactions with a specific client, meaning each request is treated as a new one, independent from the previous request for the same client.<br>
- **Caching**: The responses are stored in a temporary memory so they can be retireved faster. <br>
- **Client-server diffrentiation**: In REST API, the client (user interface) is diffrentiated from the server (bussiness logic) enabling portability, scalability, and realiability.<br>
- **Layered System**: This is hierarchical system where each individual component handles the request as it moves from your device to the server and back.<br>
- **XML, JSON, YAML**: Data format in which the request and response code is represented.<br>
- **CRUD**: Stands for Create(POST), Read(GET), Update(PUT), and Delete(Delete) operations on the REST API.
