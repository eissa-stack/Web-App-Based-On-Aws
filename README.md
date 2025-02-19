# Docker Nginx Web Application

A modern, containerized web application using Nginx, Docker, and AWS.

![Docker](https://img.shields.io/badge/Docker-Ready-blue)
![Nginx](https://img.shields.io/badge/Nginx-Stable-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 🚀 Features

- Containerized web application using Docker
- High-performance Nginx web server
- SSL/TLS support (ports 80 and 443)
- Responsive and animated web interface
- AWS deployment ready

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Docker (20.10.x or higher)
- Docker Compose (2.x or higher)
- Git
- AWS CLI (for AWS deployment)

## 🛠️ Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/docker-nginx-web.git
cd docker-nginx-web
```

2. Build and run the containers:
```bash
docker-compose up -d
```

3. Verify the application is running:
```bash
docker-compose ps
```

## 🏗️ Project Structure

```
docker-nginx-web/
├── docker-compose.yml
├── Dockerfile
├── index.html
├── README.md
└── .gitignore
```

## 🔧 Configuration

### Docker Compose Configuration
```yaml
services:
  htmlapp:
    build: . 
    ports:
      - "80:80"
      - "443:443"
```

### Dockerfile Configuration
```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/
EXPOSE 80 443
```

## 🚀 Deployment

### Local Deployment
1. Start the application:
```bash
docker-compose up -d
```

2. Access the application:
   - HTTP: `http://localhost`
   - HTTPS: `https://localhost`

### AWS Deployment
1. Connect to your EC2 instance:
```bash
ssh -i "your-key.pem" ec2-user@your-ec2-instance
```

2. Install Docker and Docker Compose
3. Clone and deploy the application
4. Configure security groups for ports 80 and 443

## 🔍 Health Check

Check if the application is running properly:
```bash
# Check container status
docker-compose ps

# View logs
docker-compose logs

# Check Nginx configuration
docker exec htmlapp nginx -t
```

## 🛑 Stopping the Application

To stop the application:
```bash
docker-compose down
```

## 🔄 Updates and Maintenance

1. Pull latest changes:
```bash
git pull origin main
```

2. Rebuild and restart containers:
```bash
docker-compose down
docker-compose up -d --build
```

## 🐛 Troubleshooting

Common issues and solutions:

1. Port conflicts:
   - Check if ports 80/443 are already in use
   - Use `netstat -tulpn | grep -E '80|443'`

2. Container fails to start:
   - Check logs: `docker-compose logs`
   - Verify Dockerfile syntax
   - Ensure all files are in correct locations

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Contributing

1. Fork the repository
2. Create your feature branch:
```bash
git checkout -b feature/amazing-feature
```
3. Commit your changes:
```bash
git commit -m 'Add amazing feature'
```
4. Push to the branch:
```bash
git push origin feature/amazing-feature
```
5. Open a Pull Request

## ✨ Acknowledgments

- Nginx documentation
- Docker community
- AWS documentation
