# 🐳 Dockerized 3-Tier WordPress App

This project demonstrates a **3-tier web architecture** using **Docker Compose**, consisting of:

- WordPress (Web Application)
- MySQL (Database)
- phpMyAdmin (Database Admin UI)

It also implements:
- Custom Docker **network**
- Persistent **volumes** for WordPress and MySQL

## 🗂 Project Structure

```
mynewapp/
├── mynewapp.yml
├── README.md
```

## 📦 Services Overview

| Service      | Image                    | Port       | Role                |
|--------------|--------------------------|------------|---------------------|
| WordPress    | `wordpress:latest`       | `8080`     | Web Frontend        |
| MySQL        | `mysql:5.7`              | Internal   | Database Backend    |
| phpMyAdmin   | `phpmyadmin/phpmyadmin`  | `8081`     | DB Admin UI         |

## 🔗 Network & Volume Configuration

- **Network:** `wp_network` (custom bridge network)
- **Volumes:**
  - `db_data`: MySQL persistent storage
  - `wp_data`: WordPress persistent storage

## 🚀 Getting Started

### 🧰 Prerequisites

- Docker
- Docker Compose

### ▶️ Run the App

```bash
docker compose -f mynewapp.yml up -d
```

### 🛑 Stop & Clean Up

```bash
docker compose -f mynewapp.yml down -v
```

## 🌐 Access the Services

- WordPress → http://localhost:8080
- phpMyAdmin → http://localhost:8081

## 📄 License

This project is licensed under the MIT License.
