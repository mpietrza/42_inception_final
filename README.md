# 42 Inception 🏗️🛡️

> Summary: This project is a hands-on introduction to infrastructure management using **Docker**. It contains tasks such as: deploying a secure, modular, and automated multi-service stack, focusing on best practices in containerization, system configuration, and orchestration. The project is built for the 42 curriculum and emphasizes understanding the principles behind DevOps, virtualization, and network security.

---

## 🏆 Features
| Category               | Services / Tools                   | Focus Areas                          |
|------------------------|------------------------------------|--------------------------------------|
| **Web & Database**     | NGINX, WordPress, MariaDB          | Deployment & Service Isolation       |
| **Infrastructure**     | Docker, Docker Compose             | Containerization & Networking        |
| **Security**           | SSL/TLS, User/Access Management    | Securing services & data             |
| **Automation**         | Bash / Shell scripts               | Automated setup/configuration        |

---

## 🔧 Build & Run

```bash
Makefile:
make #builds all the images and starts containers
make rebuild #force rebuilds without cache
make down #stops and removes all services and networks
make start #starts all the containers
make stop #stops all the containers
make logs #shows the combined logs from all containers
make ps #list all the containers in a table with the configuration info
make clean #stop and remove all containers and unused Docker resources on the system
make fclean #clean + removing all the data
make re #regenerate and restart all from scratch

Or with docker compose (from srcs folder):
docker-compose up --build #build and start infrastructure
docker-compose down #tear down services
docker-compose restart #restart all services
docker-compose up --force-recreate --build #rebuild (if necessary)
```

---

## 📂 Structure
```
inception/
├── secrets/ (empty files, used only .env)
│   ├── credentials.txt
│   ├── db_password.txt
│   └── db_root_password.txt
├── srcs/
│   ├── docker-compose.yml
│   ├── requirements/
│   │   ├── nginx/
│   │   ├── wordpress/
│   │   ├── mariadb/
│   │   └── bonus (empty)
│   └── .env
├── .dockerignore
└── Makefile
```

---

## 📝 Service Overview
| Service    | Role                                   | Key Point                            |
|------------|----------------------------------------|--------------------------------------|
| NGINX      | Web server, SSL termination            | Reverse proxy, HTTPS setup           |
| WordPress  | CMS                                    | Mounted volumes, persistent storage  |
| MariaDB    | Database for WordPress                 | Secured credentials, data volume     |


---

## 🛠️ Error Handling
- All scripts check for missing dependencies and invalid configurations.
- Container failures are flagged and reported during `docker-compose up`.
- Service healthchecks and logs enabled for debugging.

---

## 📌 Learning Outcomes
- Mastered **multi-container orchestration** with Docker Compose.
- Deepened understanding of **infrastructure security** and networking.
- Automated deployment and configuration of complex service stacks.
- Hands-on practical experience for real-world DevOps scenarios.
