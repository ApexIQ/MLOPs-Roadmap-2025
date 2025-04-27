# 📘 **Phase 2: CI/CD for Machine Learning**

## 🎯 **Phase Objective**  
Learn how to automate the training, validation, and deployment of machine learning models by building scalable CI/CD pipelines tailored for ML workflows, with proper versioning and reproducibility.

## 🧠 **Topics to Cover**

### **Why CI/CD for ML is Different**

- Understand how traditional software CI/CD pipelines differ from ML pipelines:
  - Software CI/CD mainly handles **code**.
  - ML CI/CD must handle **code + data + models + metrics**.
- Learn why it's critical to version not just code, but also:
  - **Datasets** (training/testing)
  - **Model artifacts** (trained models)
  - **Evaluation metrics** (for validation)
  - **Pipelines/configurations** (hyperparameters, environment)
- Know the importance of reproducibility:
  - Re-running a pipeline should produce the same model if no intentional changes are made.
  - Environment consistency (Python versions, library dependencies) is essential.
- Identify bottlenecks in ML without CI/CD:
  - Manual retraining
  - No rollback ability
  - Manual deployment errors
  - Missed data changes impacting model accuracy

### **Components of CI/CD in MLOps**

- **Continuous Integration (CI):**
  - Code linting and style checks.
  - Unit tests for ML code components (e.g., data loaders, preprocessing).
  - Data validation (schema, data types, outliers).
- **Continuous Delivery (CD):**
  - Automating model packaging (e.g., Docker containers).
  - Auto-evaluation of model performance before deployment.
  - Deployment to staging or production environments.
- **Continuous Training (CT):**
  - Set up retraining triggers based on new data availability or model performance drops.
  - Integrate retraining into the workflow to update models automatically.
- **Artifacts to Track:**
  - Model binaries (e.g., `.pkl`, `.onnx`)
  - Logs and metrics
  - Datasets (input/output snapshots)
  - Environment configurations (Dockerfile, Conda envs)

### **Data & Model Versioning in CI/CD**

- **Versioning Datasets:**
  - Use tools like **DVC** or **LakeFS** to track dataset changes.
  - Store dataset versions linked to Git commits.
- **Model Versioning:**
  - Register every trained model using a model registry (e.g., MLflow Model Registry).
  - Maintain metadata: training date, metrics, parameters.
- **Connecting Commits to Data/Models:**
  - Use Git commit hashes to precisely link:
    - The code used
    - The dataset used
    - The trained model produced
- **Locking Versions for Reproducibility:**
  - Ensure that models can always be retrained with the same results using saved versions of code, data, and environment.

### **Building CI/CD Pipelines for ML**

- Learn how to write ML pipelines using GitHub Actions or GitLab CI:
  - Define jobs (test → build → train → evaluate → deploy).
  - Create YAML workflows defining each stage.
- Understand pipeline stages:
  - **Test stage**: Code testing and schema validation.
  - **Build stage**: Environment setup, dependency installation.
  - **Train stage**: Model training execution.
  - **Evaluate stage**: Performance validation against thresholds.
  - **Deploy stage**: Push model to production if evaluation passes.
- Learn about unit testing for ML:
  - Test shape and type of model outputs.
  - Validate input data schema automatically.
- Know how to trigger pipelines:
  - On pull request (PR) creation or merge.
  - On commit to specific branches (e.g., `main`).
  - On scheduled time intervals (cron jobs for retraining).

### **CI/CD Tools in MLOps**

- **Code and Workflow Automation:**
  - **GitHub Actions**: Easy YAML-based automation inside GitHub.
  - **GitLab CI/CD**: Integrated pipeline runner for GitLab users.
  - **Jenkins**: Open-source automation server for complex deployments.
- **Model Versioning and Experiment Tracking:**
  - **MLflow**: For model tracking and registering.
  - **Neptune.ai**: For detailed experiment metadata tracking.
  - **SageMaker Model Registry**: AWS-managed model versioning.
- **Data Versioning:**
  - **DVC**: Data snapshots and pipeline tracking.
  - **LakeFS**: Git-like version control for S3 object stores.
- **Environment Setup:**
  - **Docker**: Containerize environments for reproducibility.
  - **Conda**: Package and manage Python dependencies easily.
  - **YAML configs**: Declare environment setups.
- **Artifact Storage:**
  - **AWS S3, MinIO, Azure Blob, GCS**: Storing model files, datasets, logs.

### **Best Practices for ML CI/CD**

- **Isolate logic**: Separate data processing, model training, evaluation, and deployment stages into different pipeline components.
- **Enforce data contracts**:
  - Validate input and output data schemas using tools like **Great Expectations**.
- **Automatically save**:
  - Trained models
  - Evaluation metrics
  - Training configurations
- **Separate training and deployment pipelines**:
  - Only deploy models that pass a strict validation stage.
- **Use tags and clear naming conventions**:
  - Tag model versions with dataset name, experiment ID, and date.
  - Version artifacts meaningfully (e.g., `model-v1.2`, `dataset-2025Q1`).

### 🛠️ **Tools Introduced**

| Category | Tools |
|----------|-------|
| CI/CD Automation | GitHub Actions, GitLab CI, Jenkins |
| Model Versioning | MLflow Registry, Neptune.ai, SageMaker Registry |
| Data Versioning | DVC, LakeFS |
| Environment Setup | Docker, Conda, YAML environment files |
| Artifact Tracking | AWS S3, Azure Blob, GCS, MinIO |
| ML Testing | Pytest, Great Expectations |

## ✅ **Phase Completion Goals**

At the end of Phase 2, students should:
- Understand the key differences between ML and traditional software CI/CD.
- Be able to version and link code, data, models, and environments.
- Build basic ML pipelines with automated testing, training, and deployment.
- Use GitHub Actions, GitLab CI, or Jenkins for ML project automation.
- Apply best practices for robust, reproducible, and secure MLOps workflows.