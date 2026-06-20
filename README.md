# 🐳 Nginx Reverse Proxy with Docker

## 📖 Project Overview
- This project demonstrates how to deploy a Python Flask application behind an Nginx Reverse Proxy using Docker Compose.
- Instead of exposing the Flask application directly to users, all incoming requests are first received by the Nginx container, which then forwards them to the backend Flask application. This architecture reflects how many production environments securely expose web applications.

## 🎯 Project Objectives
- Deploy a Python Flask application inside Docker.
- Configure Nginx as a Reverse Proxy.
- Manage multiple containers using Docker Compose.
- Understand Docker networking and container communication.
- Monitor application and Nginx logs.
- Learn a production-style deployment architecture.

## 🏗️ Project Architecture
                User
                  │
                  ▼
        Nginx Reverse Proxy
                  │
                  ▼
     Python Flask Application
- Nginx listens for client requests on port 80 and forwards them to the Flask application running on port 5000 inside another Docker container.

## 📁 Project Structure

nginx-reverse-proxy-with-docker/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── nginx/
│   └── default.conf
│
├── docker-compose.yml
├── commands.sh
├── README.md
│
└── screenshots/
    ├── 1-project-structure.png
    ├── 2-flask-app-created.png
    ├── 3-nginx-config-created.png
    ├── 4-docker-compose-created.png
    ├── 5-build-process.png
    ├── 6-containers-running.png
    ├── 7-nginx-reverse-proxy-working.png
    ├── 8-container-logs.png
    └── 9-stopping-container.png

## 📂 Project Files

### app/app.py
- Contains the Python Flask application that serves the backend web page.

### app/requirements.txt
- Lists the Python package dependencies required by the Flask application.

### app/Dockerfile
Builds the Flask application's Docker image by:
- Using the Python 3.9 Slim base image.
- Installing Flask.
- Creating a non-root user.
- Adding a container health check.
- Running the Flask application securely.

### nginx/default.conf
- Contains the Nginx Reverse Proxy configuration.
- It forwards incoming HTTP requests to the Flask container using:
- proxy_pass http://web:5000;

### docker-compose.yml
Defines both containers:
- Flask Application
- Nginx Reverse Proxy
Docker Compose automatically creates the network and allows both containers to communicate.

### commands.sh
Stores all frequently used Docker commands for building, testing, monitoring, and stopping the project.

### README.md
- Provides complete project documentation, architecture, setup instructions, and screenshots.

### - 🛠️ Technologies Used
- Ubuntu Linux
- Docker
- Docker Compose
- Nginx
- Python
- Flask

### 🚀 How to Run the Project
- Build and Start Containers
- docker compose up -d
- Verify Running Containers

### docker ps
- Test Reverse Proxy

### Open your browser:
- http://localhost

### Or run:
- curl http://localhost

### Expected output:
- Nginx Reverse Proxy Working 🚀

### View Logs
- docker compose logs

### View only Nginx logs:
- docker compose logs nginx

### View only Flask logs:

- docker compose logs web
- Stop the Project
- docker compose down

## 📋 Commands Used

- docker compose up -d

- docker ps

- docker compose logs

- docker compose logs nginx

- docker compose logs web

- curl http://localhost

- docker compose down

## 📸 Screenshots
screenshots/
├── 1-project-structure.png
├── 2-flask-app-created.png
├── 3-nginx-config-created.png
├── 4-docker-compose-created.png
├── 5-build-process.png
├── 6-containers-running.png
├── 7-nginx-reverse-proxy-working.png
├── 8-container-logs.png
└── 9-stopping-container.png

## 💡 Key Concepts Learned
Reverse Proxy Architecture
Docker Compose
Multi-Container Applications
Docker Networking
Container Communication
Flask Deployment
Nginx Configuration
Container Log Monitoring

## 🌍 Real-World Use Cases

This architecture is commonly used in production environments where:

Nginx acts as the public entry point.
Backend applications remain hidden from users.
Client requests are securely forwarded to application services.
Multiple applications can be managed behind a single reverse proxy.
Web applications are deployed using containerized infrastructure.

## 🎯 Learning Outcomes

After completing this project, I gained practical experience in:

Deploying a Python Flask application with Docker.
Configuring Nginx as a Reverse Proxy.
Managing multi-container applications using Docker Compose.
Understanding container networking.
Monitoring application and proxy logs.
Implementing a production-style deployment architecture.

## 👨‍💻 Author

Abdullah

## 📄 License

This project is created for educational, learning, and portfolio purposes.
