# 🛡️ Real-Time Payment Fraud Detection System

A high-performance, real-time fraud detection platform built with Go, TensorFlow Lite, and gRPC. Designed for sub-200ms latency and 99%+ fraud detection accuracy, this system monitors payment transactions in real time and triggers appropriate actions like blocking, challenging, or logging based on dynamic risk scores.


## 🧠 Project Description

This project detects and acts on fraudulent payment activity in real time by integrating a Go backend, machine learning inference via TensorFlow Lite, and a React-based admin dashboard. It uses synthetic data for bootstrapping the model and supports active learning via feedback loops.

Key components include:
- Real-time fraud scoring for payment events
- Admin dashboard for live monitoring and review
- Model feedback loop with false positive/negative labeling
- PCI-DSS-compliant logging and PII masking
- gRPC microservices for low-latency communication

---

## 🧱 Tech Stack

| Layer        | Tech Stack                             |
|--------------|----------------------------------------|
| Frontend     | React, Tailwind CSS, ShadCN UI         |
| Backend      | Go, gRPC, PostgreSQL                   |
| ML Inference | TensorFlow Lite (Go wrapper), Python   |
| DevOps       | Docker, Docker Compose, Makefile       |
| Security     | Masked logging, TLS, env isolation     |

---

## 🚀 Features

- ✅ Real-time transaction scoring (under 150ms)
- ✅ Risk bands with tiered response actions (block, challenge, allow)
- ✅ Stripe API integration (webhooks + inline)
- ✅ Live dashboard: filter, search, and graph risk activity
- ✅ Daily digest exports and fraud trend analytics
- ✅ Feedback loop for model retraining
- ✅ Full support for synthetic and production datasets
- ✅ PCI-DSS-aware architecture with redacted logs

---

## 📦 Folder Structure

```bash
fraud-detection-system/
├── client/          # React frontend dashboard
├── server/          # Go gRPC server + PostgreSQL integration
├── ml/              # Fraud model, data generation, TFLite serving
├── scripts/         # Test scripts, model trainer, CLI tools
├── infra/           # Terraform / PCI-DSS configs / secrets
├── docker-compose.yml
├── Makefile
├──.env.example
```


---

## 🛠️ Getting Started

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/fraud-detection-system.git
cd fraud-detection-system

# Create Python virtual environment for ML dev
python3 -m venv .venv
source .venv/bin/activate

# Install Python dependencies
pip install -r ml/requirements.txt

# Install frontend & backend dependencies
make install

# Start entire stack
docker-compose up --build

```

🧪 Development Tools
```
Python:     venv, faker, numpy, pandas
Go:         grpc, protobuf, pgx
Frontend:   vite, tailwind, shadcn/ui, chart.js
Database:   PostgreSQL 15 with audit tables
```

🔐 Security Notes
```
- PCI-DSS compliance ready
- Sensitive fields like PAN, CVV, email are masked in logs
- Secrets are stored in `.env` files or SSM Parameter Store
- TLS enforced on all network interfaces
```


