# AWS Deployment Practice Project

## 📌 Project Overview

This repository is created to demonstrate **deployment and server configuration skills** using an open-source application.
The goal of this project is to practice deploying, running, and managing a Node.js application on an **AWS EC2 instance**.

> ⚠️ The application source code is **not originally developed by me**.
> This repository is used strictly for **learning and deployment practice**.

---

## 📘 Project Attribution

Original project source:
👉 [https://github.com/verma-kunal/AWS-Session](https://github.com/verma-kunal/AWS-Session)

All rights and ownership of the original source code belong to the original author.

My contribution includes:

* Deploying the application on AWS EC2
* Configuring the Linux server environment
* Installing and managing dependencies
* Running the application using PM2
* Verifying production-level execution

---

## 🛠️ Tech Stack

* AWS EC2 (Ubuntu)
* Node.js
* npm
* PM2
* Git
* Linux Shell

---

## 🚀 Deployment Steps

### 1️⃣ Launch EC2 Instance

* Ubuntu 20.04 or later
* Open inbound ports:

  * **22** (SSH)
  * **3000** (Application)

---

### 2️⃣ Connect to Server

```bash
ssh -i your-key.pem ubuntu@<EC2_PUBLIC_IP>
```

---

### 3️⃣ Install Required Packages

```bash
sudo apt update
sudo apt install -y nodejs npm git
```

---

### 4️⃣ Clone Repository

```bash
git clone https://github.com/<your-username>/AWS-Session.git
cd AWS-Session
```

---

### 5️⃣ Install Dependencies

```bash
npm install
```

---

### 6️⃣ Configure Environment Variables

Create `.env` file:

```bash
nano .env
```

Example:

```env
PORT=3000
NODE_ENV=production
```

---

### 7️⃣ Run the Application

#### Development Mode

```bash
npm start
```

#### Production Mode (Recommended)

```bash
sudo npm install -g pm2
pm2 start server.js --name aws-session
pm2 save
pm2 startup
```

---

## 🌐 Access the Application

Open your browser and go to:

```
http://<EC2_PUBLIC_IP>:3000
```

---

## ⚠️ Important Notes

* Do **not** commit `.env` files
* Keep your AWS keys and credentials private
* Stop EC2 instances when not in use to avoid billing

---

## 📄 License

This project follows the same license as the original repository.
All rights remain with the original author.

---

If you want, I can also:
✅ Add Docker support
✅ Add Nginx reverse proxy
✅ Make this README resume-ready
✅ Add architecture diagrams

Just tell me 👍
