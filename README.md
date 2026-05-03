# End-to-End ML Wine Quality Predictor

An end-to-end Machine Learning project that predicts the quality of red wine based on physicochemical properties. Built with **MLflow** for experiment tracking, **ElasticNet** regression for modelling, and **Flask** for serving predictions via a web interface.

**Live Demo:** [GitHub Repository](https://github.com/Rajesh-Mojumder/End-to-End-ML-Wine-Quality-Predictor)

---

## Project Workflows

1. Update `config.yaml`
2. Update `schema.yaml`
3. Update `params.yaml`
4. Update the entity
5. Update the configuration manager in `src/config`
6. Update the components
7. Update the pipeline
8. Update `main.py`
9. Update `app.py`

---

## How to Run?

### STEPS:

**Clone the repository**

```bash
git clone https://github.com/Rajesh-Mojumder/End-to-End-ML-Wine-Quality-Predictor.git
cd End-to-End-ML-Wine-Quality-Predictor
```

### STEP 01 — Create a conda environment

```bash
conda create -n mlproj python=3.8 -y
conda activate mlproj
```

### STEP 02 — Install the requirements

```bash
pip install -r requirements.txt
```

### STEP 03 — Run the app

```bash
python app.py
```

Then open your browser at `http://127.0.0.1:5050`

---

## MLflow Experiment Tracking

[MLflow Documentation](https://mlflow.org/docs/latest/index.html)

To launch the MLflow UI locally:

```bash
mlflow ui
```

### DagsHub Integration

[DagsHub](https://dagshub.com/) is used for remote MLflow tracking.

To connect your own DagsHub account, set the following environment variables:

```bash
export MLFLOW_TRACKING_URI=https://dagshub.com/<YOUR_DAGSHUB_USERNAME>/End-to-End-ML-Wine-Quality-Predictor.mlflow

export MLFLOW_TRACKING_USERNAME=<YOUR_DAGSHUB_USERNAME>

export MLFLOW_TRACKING_PASSWORD=<YOUR_DAGSHUB_TOKEN>
```

> ⚠️ **Never hardcode your credentials.** Always use environment variables or GitHub Secrets.

---

## AWS CI/CD Deployment with GitHub Actions

### 1. Login to AWS Console

### 2. Create IAM User for Deployment

Required access:
- **EC2** — virtual machine for hosting
- **ECR** — Elastic Container Registry to store Docker images

### 3. Create ECR Repository

Save your ECR URI — you will need it as a GitHub Secret.

### 4. Create EC2 Machine (Ubuntu)

### 5. Install Docker on EC2

```bash
# Optional update
sudo apt-get update -y
sudo apt-get upgrade

# Required
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

### 6. Configure EC2 as Self-Hosted GitHub Runner

Go to: `Settings > Actions > Runners > New self-hosted runner`
Choose your OS and run the commands shown.

### 7. Set GitHub Secrets

In your repository go to `Settings > Secrets and variables > Actions` and add:

| Secret Name | Value |
|---|---|
| `AWS_ACCESS_KEY_ID` | Your AWS access key |
| `AWS_SECRET_ACCESS_KEY` | Your AWS secret key |
| `AWS_REGION` | e.g. `us-east-1` |
| `AWS_ECR_LOGIN_URI` | Your ECR login URI |
| `ECR_REPOSITORY_NAME` | Your ECR repo name |

---

## About MLflow

- Production-grade experiment tracking
- Traces all experiments with parameters, metrics, and artifacts
- Supports model logging, tagging, and versioning

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.8 | Core language |
| Flask | Web framework |
| MLflow | Experiment tracking & model registry |
| scikit-learn | ElasticNet regression model |
| DagsHub | Remote MLflow tracking server |
| Docker | Containerisation |
| GitHub Actions | CI/CD pipeline |
| AWS EC2 + ECR | Cloud deployment |

---

## Author

**Rajesh Mojumder**
Data Scientist & ML Engineer

- 📧 [rajesh.mojumder@g.bracu.ac.bd](mailto:rajesh.mojumder@g.bracu.ac.bd)
- 🐙 [github.com/Rajesh-Mojumder](https://github.com/Rajesh-Mojumder)
