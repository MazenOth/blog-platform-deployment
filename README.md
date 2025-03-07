
# 🏠 Blog Platform Deployment

## 📥 Installation & Deployment Guide  

### 🚀 Getting Started  

#### 1️⃣ Clone the Repository  

```sh
# Clone the repo to your local machine
git clone https://github.com/MazenOth/blog-platform-deployment.git

# Navigate into the project directory
cd blog-platform-deployment
```


#### 2️⃣ Setup Environment Variables  

##### 📌 Backend `.env`  
Create a `.env` file inside the `backend` folder and add:  

```sh
DB_HOST=db
DB_USER=appuser
DB_PASSWORD=apppassword
DB_NAME=blog_post_db
DB_PORT=3306
```

##### 📌 Frontend `.env`  
Create a `.env.local` file inside the `frontend` folder and add:  

```sh
NEXT_PUBLIC_API_BASE_URL=http://localhost:3333
```

---

#### 3️⃣ Run the Application using Docker  

Ensure **Docker** and **Docker Compose** are installed. Then, run:  

```sh
# Build and start the services
docker-compose up --build
```

This will:  

✅ Start a **MySQL database** (with health checks)  
✅ Start the **backend service**  
✅ Start the **frontend service**  

---

#### 4️⃣ Access the Application  

- **Backend API:** [http://localhost:3333](http://localhost:3333)  
- **Frontend App:** [http://localhost:3000](http://localhost:3000)  
- **Database (MySQL):** Accessible via `localhost:3307`  

---

### 🏗 Adding Blog Posts
#### 🔹 Important Guideline
Before adding a blog post, you must first create an author. Posts are linked to authors, so the system requires at least one author before blog posts can be added.

---

### 🛠 Troubleshooting  

#### 1️⃣ Database Connection Issues  

```sh
# Ensure MySQL is running
docker ps

# Check logs for errors
docker logs blogpost-mysql
```

#### 2️⃣ Backend Fails to Connect to MySQL  

```sh
# Ensure the backend waits for the database to be ready
docker-compose restart backend
```

#### 3️⃣ Frontend Not Fetching Data  

Ensure API requests are going to `http://localhost:3333`, not `http://blogpost-backend:3333` in **client-side code**.

---

### 🎯 Assumptions  

✅ MySQL is used as the primary database.  
✅ Backend and frontend are containerized using Docker.  
✅ API requests must be handled differently in **client** vs. **server** components in Next.js.  

---

💡 _Blog Platform project should now be successfully deployed and accessible! 🚀_
