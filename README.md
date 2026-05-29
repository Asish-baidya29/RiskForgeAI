# RiskForgeAI
Production-grade MLOps pipeline for vehicle insurance risk prediction using MongoDB, FastAPI, CI/CD, GitHub Actions, and AWS. Includes data ingestion, training pipeline, model deployment, logging, and scalable prediction workflows for real-world ML system design.


# RiskForgeAI 🚗⚙️

An end-to-end production-ready MLOps pipeline for vehicle insurance risk prediction using FastAPI, MongoDB, Docker, GitHub Actions, and AWS.

This project demonstrates how real-world machine learning systems are built, automated, validated, deployed, and monitored in production environments. It covers the complete ML lifecycle — from data ingestion and validation to model training, deployment, CI/CD automation, and scalable prediction serving.

---

# 📌 Project Highlights

* End-to-end MLOps workflow
* MongoDB Atlas integration
* Modular training pipeline architecture
* Automated data validation and transformation
* Machine learning model training and evaluation
* AWS S3 model versioning and storage
* FastAPI prediction service
* Dockerized deployment
* CI/CD automation using GitHub Actions
* AWS EC2 + ECR deployment pipeline
* Production-style logging and exception handling

---

# 🏗️ Project Architecture

```text
Data Source (MongoDB)
        ↓
Data Ingestion
        ↓
Data Validation
        ↓
Data Transformation
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Model Pusher (AWS S3)
        ↓
FastAPI Prediction Service
        ↓
Docker + GitHub Actions CI/CD
        ↓
AWS EC2 Deployment
```

---

# 📂 Project Structure

```text
RiskForgeAI/
│
├── app.py
├── requirements.txt
├── setup.py
├── pyproject.toml
├── Dockerfile
├── .dockerignore
│
├── notebook/
├── templates/
├── static/
├── config/
├── artifacts/
├── logs/
│
├── src/
│   ├── components/
│   ├── configuration/
│   ├── constants/
│   ├── data_access/
│   ├── entity/
│   ├── exception/
│   ├── logger/
│   ├── pipeline/
│   ├── aws_storage/
│   └── utils/
│
└── .github/workflows/
```

---

# ⚙️ Tech Stack

## Backend & ML

* Python
* Scikit-learn
* Pandas
* NumPy
* FastAPI

## Database

* MongoDB Atlas

## Cloud & Deployment

* AWS EC2
* AWS ECR
* AWS S3

## DevOps & Automation

* Docker
* GitHub Actions
* CI/CD Pipelines

---

# 🚀 Getting Started

## 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd RiskForgeAI
```

---

## 2️⃣ Create Virtual Environment

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

Verify installation:

```bash
pip list
```

---

# 🍃 MongoDB Setup

## Create MongoDB Atlas Cluster

1. Create a MongoDB Atlas account
2. Create a new project
3. Create a free M0 cluster
4. Configure database username/password
5. Allow access from:

```text
0.0.0.0/0
```

6. Copy the MongoDB connection string

Example:

```text
mongodb+srv://<username>:<password>@cluster.mongodb.net/
```

---

## Set Environment Variable

### Bash

```bash
export MONGODB_URL="your_mongodb_connection_string"
```

### PowerShell

```powershell
$env:MONGODB_URL="your_mongodb_connection_string"
```

---

# 📥 Data Ingestion

The ingestion pipeline fetches vehicle insurance data from MongoDB and stores it locally for downstream processing.

Main modules:

* `mongo_db_connections.py`
* `data_ingestion.py`
* `data_access/`

Features:

* MongoDB integration
* Artifact generation
* Config-driven ingestion pipeline

---

# ✅ Data Validation

The validation stage checks:

* Missing values
* Data types
* Schema consistency
* Column validation

Schema definitions are maintained in:

```text
config/schema.yaml
```

---

# 🔄 Data Transformation

The transformation pipeline handles:

* Feature engineering
* Encoding
* Missing value handling
* Scaling and preprocessing

Generated preprocessing objects are stored for inference consistency.

---

# 🤖 Model Training

The training pipeline:

* Splits training/testing datasets
* Trains ML models
* Evaluates performance
* Saves trained artifacts

Supported features:

* Modular trainer design
* Config-driven training
* Reusable estimator classes

---

# ☁️ AWS Integration

## AWS Services Used

* AWS S3 → Model storage
* AWS ECR → Docker image registry
* AWS EC2 → Deployment server

---

## Configure AWS Credentials

### Bash

```bash
export AWS_ACCESS_KEY_ID="YOUR_ACCESS_KEY"
export AWS_SECRET_ACCESS_KEY="YOUR_SECRET_KEY"
```

### PowerShell

```powershell
$env:AWS_ACCESS_KEY_ID="YOUR_ACCESS_KEY"
$env:AWS_SECRET_ACCESS_KEY="YOUR_SECRET_KEY"
```

---

# 📦 Model Versioning with S3

The project supports:

* Uploading trained models to S3
* Pulling latest production models
* Model version management

S3 bucket example:

```text
my-model-mlopsproj
```

---

# 🌐 FastAPI Prediction Service

The application exposes prediction APIs using FastAPI.

Run locally:

```bash
python app.py
```

Default server:

```text
http://0.0.0.0:5000
```

---

# 🐳 Docker Setup

Build Docker image:

```bash
docker build -t riskforgeai .
```

Run container:

```bash
docker run -p 5000:5000 riskforgeai
```

---

# 🔄 CI/CD with GitHub Actions

GitHub Actions automates:

* Docker image build
* AWS ECR push
* EC2 deployment

Required GitHub Secrets:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
```

---

# 🖥️ AWS EC2 Deployment

## Deployment Steps

### 1. Launch EC2 Instance

* Ubuntu preferred
* Open required ports

### 2. Install Docker

```bash
sudo apt update
sudo apt install docker.io
```

### 3. Configure GitHub Self-Hosted Runner

Connect EC2 with GitHub Actions runner.

### 4. Open Application Port

```text
5080
```

Access application:

```text
http://<EC2_PUBLIC_IP>:5080
```

---

# 📊 Pipeline Workflow

```text
MongoDB
   ↓
Data Ingestion
   ↓
Data Validation
   ↓
Data Transformation
   ↓
Model Training
   ↓
Model Evaluation
   ↓
AWS S3 Model Storage
   ↓
FastAPI Deployment
   ↓
Docker + GitHub Actions CI/CD
   ↓
AWS EC2 Production Deployment
```

---

# 📌 Key Learning Outcomes

This project demonstrates practical experience with:

* Production-grade MLOps architecture
* Real-world ML pipeline orchestration
* Cloud deployment workflows
* CI/CD automation
* Containerized applications
* Scalable prediction services
* Model lifecycle management
* Software engineering best practices for ML systems

---

# 📬 Contact

If you found this project useful or want to collaborate on MLOps, Machine Learning, or AI systems, feel free to connect.

---

# ⭐ Final Note

RiskForgeAI is designed as a portfolio-quality MLOps project that reflects how modern machine learning systems are developed and deployed in industry environments.

