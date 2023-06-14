# Instant Messaging System

This is a demo and template for backend assignment of 2023 TikTok Tech Immersion.

Installation
Requirement:

golang 1.18+
docker
To install dependency tools:

make pre
Run
docker-compose up -d
Check if it's running:

curl localhost:8080/ping


This is a backend implementation of an Instant Messaging (IM) system. The system consists of two services: an HTTP server and an RPC server. It allows users to send and receive messages using the provided APIs.

## Architecture

The system follows a client-server architecture with the following components:

- HTTP Server: Responsible for handling HTTP requests and exposing the HTTP API endpoints.
- RPC Server: Handles remote procedure calls (RPC) and provides additional functionality not covered by the HTTP API.
- Data Storage: Messages are stored in Redis for retrieval by the receivers.

## Technologies Used

- Programming Language: Go
- Database: Redis

## API Documentation

The API documentation can be found in the [idl_http.proto](idl_http.proto) file. It provides detailed information about the available HTTP API endpoints and their usage.

### Example API Usage

#### Send Message

To send a message from user `a` to user `b`, use the following API endpoint:

POST /api/send?sender=a&receiver=b&text=hi


#### Pull Messages

To retrieve messages from the chat between user `a` and user `b`, use the following API endpoint:

GET /api/pull?chat=a:b

Scalability and Performance
The Instant Messaging system is designed to handle a large number of users and messages. It supports concurrent requests and can scale elastically when deployed.

Testing
The system has been tested for performance and stress using the provided GitHub Actions workflow. The workflow can be found in the .github/workflows/test.yml file.

Repository Structure
http-server/: Contains the code for the HTTP server implementation.
rpc-server/: Contains the code for the RPC server implementation.
docker-compose.yml: Defines the Docker Compose configuration for running the system.
idl_http.proto: Contains the IDL (Interface Definition Language) for the HTTP API.
idl_rpc.thrift: Contains the IDL for the RPC API.
.github/workflows/test.yml: GitHub Actions workflow for testing the system.
Contributions
Contributions to this project are welcome. If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request.

License
This project is licensed under the MIT License.