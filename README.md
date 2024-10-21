
# Slim KV Store

[![Build Status](https://img.shields.io/github/actions/workflow/status/yourusername/slim-kv-store/ci.yml?branch=main)](https://github.com/yourusername/slim-kv-store/actions)
[![License](https://img.shields.io/github/license/yourusername/slim-kv-store)](LICENSE)

A lightweight, scalable key-value store implementing consistent hashing in Java. **Slim KV Store** is designed to be simple, efficient, and easy to deploy, providing a solid foundation for learning about distributed systems and building more complex applications.

## Table of Contents
* [Features](#features)
* [Getting Started](#getting-started)
    * [Prerequisites](#prerequisites)
    * [Installation](#installation)
        * [From Source](#from-source)
        * [Using Docker](#using-docker)
        * [Using Homebrew (macOS)](#using-homebrew-macos)
        * [Using DEB/RPM Packages](#using-debrpm-packages)
    * [Configuration](#configuration)
* [Usage](#usage)
    * [Running the Application](#running-the-application)
    * [API Endpoints](#api-endpoints)
        * [PUT /kv/:key](#put-kvkey)
        * [GET /kv/:key](#get-kvkey)
        * [DELETE /kv/:key](#delete-kvkey)
* [Examples](#examples)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

---

## Features

- **Consistent Hashing:** Implements a consistent hashing algorithm for efficient key distribution.
- **RESTful API:** Provides a simple HTTP API for interacting with the key-value store.
- **In-Memory Storage:** Uses an in-memory data structure for quick data access.
- **Modular Design:** Clean code structure for easy maintenance and scalability.
- **Cross-Platform Support:** Runs on any system with Java installed.
- **Multiple Deployment Options:** Available as a JAR file, Docker image, DEB/RPM packages, and more.

---

## Getting Started

### Prerequisites

- **Java 11** or higher
- **Git** (if installing from source)

### Installation

#### From Source

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/slim-kv-store.git
   cd slim-kv-store
   ```

2. **Build the project using Maven or Gradle:**

   - **Using Maven:**

     ```bash
     mvn clean package
     ```

   - **Using Gradle:**

     ```bash
     gradle clean build
     ```

3. **Run the application:**

   ```bash
   java -jar target/slim-kv-store-1.0.0.jar
   ```

#### Using Docker

1. **Pull the Docker image:**

   ```bash
   docker pull yourusername/slim-kv-store:latest
   ```

2. **Run the Docker container:**

   ```bash
   docker run -d -p 8080:8080 yourusername/slim-kv-store:latest
   ```

#### Using Homebrew (macOS)

1. **Tap the repository:**

   ```bash
   brew tap yourusername/slim-kv-store
   ```

2. **Install Slim KV Store:**

   ```bash
   brew install slim-kv-store
   ```

3. **Run the application:**

   ```bash
   slim-kv-store
   ```

#### Using DEB/RPM Packages

- **DEB Package (Debian/Ubuntu):**

  ```bash
  sudo dpkg -i slim-kv-store_1.0.0_amd64.deb
  ```

- **RPM Package (CentOS/Fedora):**

  ```bash
  sudo rpm -ivh slim-kv-store-1.0.0-1.x86_64.rpm
  ```

### Configuration

- **Default Configuration File:** `application.properties`
- **Environment Variables:**

  - `SERVER_PORT`: Port on which the server listens (default `8080`).
  - `LOG_LEVEL`: Logging level (e.g., `INFO`, `DEBUG`).

- **Command-Line Arguments:**

  ```bash
  java -jar slim-kv-store-1.0.0.jar --server.port=9090 --log.level=DEBUG
  ```

---

## Usage

### Running the Application

- **Start the Server:**

  ```bash
  java -jar slim-kv-store-1.0.0.jar
  ```

- **Server Running Message:**

  ```
  Slim KV Store is running on port 8080
  ```

### API Endpoints

#### PUT /kv/:key

- **Description:** Store a value with the specified key.
- **Request:**

  ```http
  PUT /kv/myKey
  Content-Type: application/json

  {
    "value": "myValue"
  }
  ```

- **Response:**

  ```json
  {
    "message": "Key stored successfully"
  }
  ```

#### GET /kv/:key

- **Description:** Retrieve the value associated with the specified key.
- **Request:**

  ```http
  GET /kv/myKey
  ```

- **Response:**

  ```json
  {
    "value": "myValue"
  }
  ```

#### DELETE /kv/:key

- **Description:** Delete the key-value pair associated with the specified key.
- **Request:**

  ```http
  DELETE /kv/myKey
  ```

- **Response:**

  ```json
  {
    "message": "Key deleted successfully"
  }
  ```

---

## Examples

- **Store a Value:**

  ```bash
  curl -X PUT -H "Content-Type: application/json" -d '{"value": "hello world"}' http://localhost:8080/kv/greeting
  ```

- **Retrieve a Value:**

  ```bash
  curl http://localhost:8080/kv/greeting
  ```

- **Delete a Value:**

  ```bash
  curl -X DELETE http://localhost:8080/kv/greeting
  ```

---

## Roadmap

- **Multi-Node Support:** Expand to a distributed system with multiple nodes.
- **Advanced Features:**
  - Full-text search capabilities.
  - Time-series data support.
  - Enhanced security features.
- **Performance Optimization:** Improve latency and throughput.
- **Persistence Layer:** Add options for persistent storage.

---

## Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](docs/CONTRIBUTING.md) file for guidelines on how to get involved.

1. **Fork the Repository**

2. **Create a Feature Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Commit Your Changes**

   ```bash
   git commit -m "Add your message here"
   ```

4. **Push to Your Branch**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Contact

**Your Name**

- **Email:** [karthikrajkumar.kannan@gmail.com](mailto:karthikrajkumar.kannan@gmail.com)
- **GitHub:** [karthikrajkumar](https://github.com/karthikrajkumar)

Feel free to reach out with questions, suggestions, or just to say hello!

---


