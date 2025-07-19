# 🐳 Dockerized 3-Tier WordPress App (WordPress + MySQL + phpMyAdmin)

This project demonstrates a complete **3-tier architecture** using Docker Compose. It includes:

- WordPress (Frontend Web)
- MySQL (Backend Database)
- phpMyAdmin (Database Admin UI)
- Custom Docker network and persistent volumes

---

## 📁 Project Structure

```
mynewapp/
├── mynewapp.yml       # Docker Compose configuration
├── README.md          # Project documentation
```

---

## ⚙️ Step-by-Step Setup

### 🔹 Step 1: Clone or Download the Repo

```bash
git clone https://github.com/yourusername/mynewapp.git
cd mynewapp
```

> 📸 _Screenshot path_: `screenshots/step1-clone.png`

---

### 🔹 Step 2: Start the Containers

```bash
docker compose -f mynewapp.yml up -d
```

- This will pull necessary images (if not already present) and start all containers.

> 📸 _Screenshot path_: `screenshots/step2-up.png`

---

### 🔹 Step 3: Check Running Containers

```bash
docker ps
```

You should see 3 containers: `wordpress_app`, `mysql_db`, and `phpmyadmin_ui`.

> 📸 _Screenshot path_: `screenshots/step3-docker-ps.png`

---

### 🔹 Step 4: Access the Applications

- WordPress → [http://localhost:8080](http://localhost:8080)
- phpMyAdmin → [http://localhost:8081](http://localhost:8081)

> 📸 _Screenshot path_: `screenshots/step4-wordpress-browser.png`

---

### 🔹 Step 5: phpMyAdmin Login

- **Username:** wpuser
- **Password:** wppass

> 📸 _Screenshot path_: `screenshots/step5-phpmyadmin-login.png`

---

## 📦 Docker Volumes

Persistent data is stored in named volumes:

- `db_data`: MySQL data
- `wp_data`: WordPress uploads/themes

```bash
docker volume ls
```

> 📸 _Screenshot path_: `screenshots/step6-volumes.png`

---

## 🧹 Cleanup

To stop and remove all containers, networks, and volumes:

```bash
docker compose -f mynewapp.yml down -v
```

> 📸 _Screenshot path_: `screenshots/step7-cleanup.png`

---

## 🔒 Security Tips

- Change default passwords in production.
- Consider using secrets and env files.
- Use NGINX + HTTPS for secure access.

---

## 🧑‍💻 Author

**Your Name**  
🔗 GitHub: [@yourusername](https://github.com/yourusername)

---

## 📄 License

Licensed under the MIT License.
