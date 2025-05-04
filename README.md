 **Docker Build Projects & Practice Codes**  | DevOps practice! 🐳💻

---

## 🐳 Docker Build Projects & Practice Code Examples

---

### 🔰 **1. Simple Node.js Web App** — `docker-node-basic`

🚀 **Tech**: Node.js + Express
🎯 **Goal**: Build & run a basic web server

📁 **Structure**:

```
docker-node-basic/
├── Dockerfile
├── app.js
├── package.json
```

🧱 **Dockerfile**:

```dockerfile
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["node", "app.js"]
EXPOSE 3000
```

▶️ **Run**:

```bash
docker build -t node-app .
docker run -p 3000:3000 node-app
```

---

### 🔥 **2. Python Flask App + Docker Compose** — `docker-python-flask`

🐍 **Tech**: Python + Flask
⚙️ **Tools**: Docker Compose

📁 **Structure**:

```
docker-python-flask/
├── app/
│   ├── app.py
│   └── requirements.txt
├── Dockerfile
└── docker-compose.yml
```

🧱 **Dockerfile**:

```dockerfile
FROM python:3.10
WORKDIR /app
COPY app/ .
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
EXPOSE 5000
```

🔧 **docker-compose.yml**:

```yaml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "5000:5000"
```

---

### 🐘 **3. MERN Stack Full-Stack App** — `docker-mern-stack`

🌐 **Tech**: MongoDB + Express + React + Node
🧩 **Services**: Frontend, Backend, Database

📁 **Structure**:

```
docker-mern-stack/
├── client/
│   ├── Dockerfile
│   └── src/
├── server/
│   ├── Dockerfile
│   └── index.js
├── docker-compose.yml
```

🔧 **docker-compose.yml**:

```yaml
version: '3.8'
services:
  frontend:
    build: ./client
    ports:
      - "3000:3000"
  backend:
    build: ./server
    ports:
      - "5000:5000"
    depends_on:
      - mongo
  mongo:
    image: mongo
    ports:
      - "27017:27017"
```

---

### 📊 **4. PHP + MySQL Web App (LAMP Stack)** — `docker-lamp-stack`

🌐 **Tech**: Apache + PHP + MySQL

📁 **Structure**:

```
docker-lamp-stack/
├── html/
│   └── index.php
├── docker-compose.yml
```

🔧 **docker-compose.yml**:

```yaml
version: '3.8'
services:
  web:
    image: php:8.1-apache
    volumes:
      - ./html:/var/www/html
    ports:
      - "8080:80"

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: rootpass
      MYSQL_DATABASE: mydb
```

---

### 🐍 **5. Django + PostgreSQL App** — `docker-django-postgres`

🧠 **Tech**: Django + PostgreSQL
🔄 **Tools**: Docker Compose

🔧 **docker-compose.yml**:

```yaml
version: '3'
services:
  web:
    build: .
    command: python manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - "8000:8000"
    depends_on:
      - db

  db:
    image: postgres
    environment:
      POSTGRES_DB: mydb
      POSTGRES_USER: user
      POSTGRES_PASSWORD: pass
```

---

### 🛠️ **6. NGINX + Static Website** — `docker-nginx-static-site`

📄 **Tech**: NGINX + HTML/CSS
🧘‍♂️ **Use Case**: Deploy static portfolio or landing page

📁 **Structure**:

```
docker-nginx-static-site/
├── html/
│   └── index.html
├── nginx.conf
└── Dockerfile
```

🧱 **Dockerfile**:

```dockerfile
FROM nginx:alpine
COPY html/ /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
```

---


