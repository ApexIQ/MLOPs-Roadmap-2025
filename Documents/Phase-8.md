# 📘 **Phase 8: Platform-Specific MLOps (Azure & GCP)**

## 🎯 **Phase Objective**
Understand how MLOps practices are implemented on major cloud platforms like **Azure ML** and **Google Cloud Vertex AI**, learn managed services, deployment pipelines, monitoring tools, and get introduced to Infrastructure as Code (IaC) for ML workflows.

## 🧠 **Topics to Cover**

### **MLOps in the Cloud: Key Concepts**

- Why Cloud-Native MLOps?
  - **Scalability**: Easily scale compute for training and serving.
  - **Security**: Built-in IAM, networking, encryption standards.
  - **Auditability**: Logs, versioning, monitoring built into cloud services.
  - **Collaboration**: Share datasets, models, endpoints across teams.
- Key Cloud Concepts:
  - **Managed Pipelines**: Create retraining/evaluation pipelines without handling low-level infra.
  - **Hosted Endpoints**: Deploy models as APIs easily.
  - **Registries**: Store versions of datasets, models, and features.
  - **Monitoring and Retraining**: Automate detection and handling of model decay or drift.

### **MLOps on Azure Machine Learning**

- Azure ML Studio Overview:
  - Visual interface to manage datasets, experiments, models, and endpoints.
- Using the Azure ML SDK (Python):
  - Programmatically interact with Azure ML resources (datasets, models, jobs).
- ML Pipeline Creation:
  - **Designer**: Drag-and-drop low-code pipeline creation.
  - **Code-based**: Define pipelines using Python SDKs for full flexibility.
- Model Registry and Versioning:
  - Save multiple versions of models.
  - Manage production model versions safely.
- Real-Time & Batch Deployment:
  - Deploy models as **real-time APIs** or **batch processing jobs**.
- Monitoring and Alerting:
  - Use **Azure Monitor** to track performance, drift, latency, errors.
- Managing Environments and Dependencies:
  - Define environments with Conda/YAML files.
  - Use Docker images for reproducibility across jobs.

> *Students should practice registering a model and deploying an endpoint via Azure ML.*

### **MLOps on Google Cloud Vertex AI**

- Vertex AI Overview:
  - Unified ML platform for data management, model building, training, serving.
- Managed Datasets, Models, Experiments:
  - Full lifecycle tracking with metadata integration.
- Vertex AI Pipelines:
  - Orchestrate end-to-end ML workflows (powered by **Kubeflow Pipelines**).
- Training Jobs:
  - Submit **custom training jobs** or use **AutoML** (low-code model training).
- Endpoint Creation and Scaling:
  - Deploy models to managed endpoints with auto-scaling options.
  - Monitor request load, scale up/down automatically.
- Monitoring Model Performance and Drift:
  - Setup drift detection and performance monitoring dashboards.
- Feature Store and Metadata Tracking:
  - Manage versioned features across datasets and models.
  - Track lineage between raw data → features → model versions.

> *Students should explore Vertex AI Workbench and experiment tracking features.*

### **Comparing Azure vs GCP vs Open Source**

| Category | Azure ML | Vertex AI | Open Source Tools |
|----------|----------|-----------|-------------------|
| Pipelines | Designer + SDK | Kubeflow Pipelines | Airflow, Kubeflow |
| Model Serving | Managed Endpoints | Managed Endpoints | FastAPI, TorchServe |
| Monitoring | Azure Monitor | Vertex AI Metrics | Prometheus, Grafana |
| Feature Store | Built-in | Built-in | Custom solutions |
| Infrastructure Control | Moderate (Bicep, Terraform) | Strong (Terraform) | Full control |

- Understand trade-offs between full-managed platforms vs open-source custom setups.
- Cost, flexibility, security, and scaling considerations.

### **Infrastructure as Code (IaC) (Intro)**

- Why Infrastructure as Code is Critical:
  - Ensures **reproducibility** of ML environments.
  - Enables **compliance** and **auditability**.
  - Fast, version-controlled deployment of full ML systems.
- Common IaC Tools:
  - **Azure**:
    - **ARM Templates**: JSON-based infra descriptions.
    - **Bicep**: Simplified syntax over ARM templates.
  - **Google Cloud**:
    - **Deployment Manager**: YAML/JSON templates for infra.
    - **Terraform**: Cross-cloud IaC tool (very popular in MLOps).
- IaC Use Cases for MLOps:
  - Define and deploy training clusters.
  - Setup serving endpoints and monitoring pipelines.
  - Version infra changes alongside code (in Git repos).

> *Students should read an example Terraform script for deploying an ML training environment.*


### 🛠️ **Tools Introduced**

| Category | Tools |
|----------|-------|
| Cloud MLOps Platforms | Azure ML, Vertex AI |
| SDKs | azureml-sdk (Python), google-cloud-aiplatform (Python) |
| Pipeline Orchestration | Azure ML Pipelines, Vertex AI Pipelines (Kubeflow) |
| Monitoring | Azure Monitor, Vertex AI Dashboards |
| Infrastructure as Code (IaC) | Bicep, ARM Templates, Terraform, GCP Deployment Manager |
| Deployment | Managed Endpoints (Azure & GCP), Autoscaling services |

## ✅ **Phase Completion Goals**

At the end of Phase 8, students should:
- Understand how MLOps is implemented in Azure and Google Cloud.
- Create ML pipelines, register models, and deploy APIs using managed cloud services.
- Monitor and scale ML models in production cloud environments.
- Compare cloud-native vs open-source MLOps trade-offs.
- Get introduced to using Infrastructure as Code for reproducible ML deployments.