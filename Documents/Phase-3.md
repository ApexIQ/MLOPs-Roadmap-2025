# 📘 **Phase 3: Experiment Tracking & Model Management**

## 🎯 **Phase Objective**  
Learn how to track, organize, compare, and manage ML experiments systematically to ensure reproducibility, effective collaboration, and efficient model selection.

## 🧠 **Topics to Cover**

### **The Need for Experiment Tracking**

- Understand why tracking ML experiments is critical:
  - Challenges without tracking:
    - “Which model was best?” confusion after multiple experiments.
    - Forgotten hyperparameters and setups between experiments.
    - Losing track of which dataset or preprocessing step was used.
- Manual vs automated logs:
  - Manual logs (e.g., Excel sheets, notes) are error-prone, incomplete, and hard to scale.
  - Automated tracking ensures consistent, searchable, and rich experiment history.
- Key elements to track for every experiment:
  - **Parameters** (e.g., learning rate, batch size)
  - **Metrics** (e.g., accuracy, loss, F1-score)
  - **Datasets** used (version IDs, preprocessing details)
  - **Code version** (Git commit hash, branch)
  - **Hardware/Environment** (CPU/GPU, library versions)

### **Tools for Experiment Tracking**

- Learn and compare the most popular tracking tools:
  - **MLflow Tracking**: Lightweight, open-source, flexible.
  - **Weights & Biases (W&B)**: Powerful visualizations, collaboration features.
  - **Neptune.ai**: Experiment metadata tracking at scale.
  - **Comet.ml**: Online dashboards for experiment logging.
  - **TensorBoard**: Visualization mainly for deep learning training (TensorFlow, PyTorch).
  - **Sacred**: Lightweight tracking framework.
- Key features across tools:
  - Real-time dashboards
  - Parameter logging
  - Run comparisons
  - Artifact (models, outputs) storage
  - Filters, groups, tags for easy organization

### **Using MLflow for Local & Remote Tracking**

- Core concepts in MLflow Tracking:
  - **Run**: Single training execution
  - **Experiment**: A collection of related runs
  - **Artifact**: Files like models, plots, logs saved during a run
- How to log from code using MLflow:
  - Log parameters: `mlflow.log_param('learning_rate', 0.001)`
  - Log metrics: `mlflow.log_metric('accuracy', 0.93)`
  - Save artifacts: model files, plots
- How to organize experiments:
  - Use tags (e.g., dataset version, model type).
  - Group runs under logical experiment names.
- Setting up a remote MLflow server (optional):
  - Configure a backend store (PostgreSQL, MySQL).
  - Use a blob store (S3, Azure, GCP) for artifact storage.
  - Enable team-wide experiment sharing.

### **Weights & Biases for Rich Experiment Tracking**

- Setting up W&B:
  - Install with `pip install wandb`
  - Login/authenticate with your W&B account.
- Key W&B capabilities:
  - **Project Dashboard**: View all experiments grouped under projects.
  - **Realtime Monitoring**: See live training metrics and logs.
  - **Artifact Logging**: Save and version models, datasets, plots.
  - **Historical Comparisons**: Compare past runs visually across metrics.
  - **Grouping and Filtering**: Organize experiments based on parameters or performance.

### **Model Versioning and Model Registry**

- What is a Model Registry?
  - A system to track model versions through stages like Staging, Production, Archived.
  - Keeps history of model evaluations and metadata.
  - Links models to training parameters, datasets, and code versions.
- Benefits of Model Registry:
  - Promote models safely from Staging to Production based on metrics.
  - Maintain **audit trails** for compliance and debugging.
  - Enable **rollback** to previous model versions if needed.
- Tools for Model Registry:
  - **MLflow Model Registry**: Simple and flexible.
  - **Weights & Biases Artifacts**: Robust lineage tracking and diffs.
  - **SageMaker Model Registry**: AWS-native, production-grade.

### **Best Practices for Experimentation**

- Set clear experiment goals before running (e.g., improve recall by 5%).
- Use automation or scripts to launch and track experiments (e.g., MLflow Projects).
- Store configurations (parameters, dataset versions) externally in YAML/JSON files.
- Version control:
  - Code: Git repos
  - Data: DVC or similar tools
  - Models: MLflow, W&B, S3 buckets
- Link each experiment run with a Git commit hash for complete reproducibility:
  - Use `git rev-parse HEAD` in your training script to capture commit ID.

### 🛠️ **Tools Introduced**

| Category | Tools |
|----------|-------|
| Tracking | MLflow Tracking, Weights & Biases (W&B), TensorBoard |
| Logging | Python logging, CLI commands, API-based logging |
| Model Registry | MLflow Registry, W&B Artifacts, SageMaker Registry |
| Experiment Visualization | MLflow UI, W&B Dashboards, Comet.ml Projects |


## ✅ **Phase Completion Goals**

At the end of Phase 3, students should:
- Understand the importance of systematic experiment tracking.
- Set up and use tools like MLflow and W&B for local and remote tracking.
- Compare and organize multiple model experiments easily.
- Register and version trained models safely for deployment.
- Apply best practices to automate and reproduce experiments consistently.