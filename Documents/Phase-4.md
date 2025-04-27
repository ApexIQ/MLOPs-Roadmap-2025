# 📘 **Phase 4: Workflow Orchestration & Pipelines**

## 🎯 **Phase Objective**
Learn to design, automate, and monitor ML workflows using orchestration tools like **Apache Airflow**, **Prefect**, and **Kubeflow Pipelines**, focusing on building scalable, fault-tolerant, and modular ML pipelines.

## 🧠 **Topics to Cover**

### **Why ML Pipelines Are Critical**

- Understand challenges with ad-hoc ML workflows:
  - **Code Duplication**: Repeating similar scripts for every run.
  - **Manual Re-runs**: Running steps manually introduces human error.
  - **No Tracking/Logging**: Difficulty in diagnosing failures or understanding history.
  - **No Modularity**: Changes in one step often break other parts.
- Learn the benefits of ML pipelines:
  - **Reusability**: Modular steps can be reused across projects.
  - **Monitoring**: Automatic visibility into execution status and errors.
  - **Scheduled Execution**: Regular data ingestion, retraining, evaluation without manual triggers.
  - **Fault-tolerant Recovery**: Resume from point of failure rather than restarting the workflow.
- Understand the difference between ML pipelines and software build pipelines:
  - ML pipelines handle **data transformations, model training, evaluation, deployment**.
  - Software pipelines handle **code compilation, unit testing, building binaries**.

### **Understanding DAGs (Directed Acyclic Graphs)**

- What is a DAG:
  - **Directed Acyclic Graph**: a structure representing tasks that must follow a specific execution order without forming loops.
- Learn key DAG elements:
  - **Nodes**: Tasks like data preprocessing, model training.
  - **Dependencies**: Order of execution based on task outputs/inputs.
  - **Triggers**: Scheduled, manual, or event-based starts.
- Learn DAG execution principles:
  - Parallelism: Tasks without dependencies can run simultaneously.
  - Sequential Execution: Dependent tasks follow their parent completion.
- Study failure recovery strategies:
  - Retry failed tasks automatically.
  - Skip or alert on failure conditions.
  - Backfilling missed runs if scheduled execution failed.

### **Apache Airflow for ML Workflows**

- Installing Apache Airflow:
  - Preferred setup using **Docker Compose**.
  - Understand Airflow web server, scheduler, and metadata DB components.
- Creating DAGs using Python:
  - Define tasks using Python Operators (e.g., `PythonOperator`, `BashOperator`).
  - Set up task dependencies programmatically.
- Scheduling and monitoring:
  - Define schedules using cron syntax or Airflow presets (e.g., `@daily`, `@hourly`).
  - Monitor DAG runs, task logs, retries from Airflow UI.
- Triggering model training:
  - Schedule model retraining jobs automatically.
  - Trigger training manually via API or UI if needed.
- Logging task success/failure:
  - Airflow automatically logs start times, end times, failures, retries.
  - Set up notifications for task failures (email, Slack).

### **Prefect and Lightweight Alternatives**

- Overview of Prefect vs Airflow:
  - **Prefect** uses dynamic flows; easier to manage and configure than Airflow.
  - Less setup overhead for small to medium projects.
- Key Prefect concepts:
  - **Flows**: The entire workflow (similar to a DAG).
  - **Tasks**: Individual steps inside a flow.
- CLI and Dashboard:
  - Prefect Orion provides local UI for monitoring and execution.
  - Use CLI to start and monitor flows locally.
- Using Prefect Cloud (optional):
  - Manage larger workflows with free or paid Prefect Cloud service.
- When to use Prefect over Airflow:
  - Quick setup needs.
  - Flexible scheduling and dependency management.
  - Projects without heavy Kubernetes/enterprise needs.

### **Kubeflow Pipelines (Advanced Orchestration)**

- Use-cases for Kubeflow:
  - Large-scale ML operations where Kubernetes is already used.
  - Need for scalable, reproducible, distributed training workflows.
- Core Kubeflow concepts:
  - **Component**: Encapsulated Docker container executing a single ML task.
  - **Pipeline**: Group of components connected through inputs and outputs.
  - **Steps**: Units of execution inside a pipeline.
- Integration with KFP UI:
  - Track execution metrics, parameters, artifacts.
  - Visualize pipeline runs and debug failures.
- Building pipeline components:
  - Write Python functions, containerize them, define as pipeline steps.
- Tracking runs and artifacts:
  - Automatically track parameters, metrics, model files through Kubeflow’s metadata store.

### **Best Practices in Pipeline Design**

- Separate logic into modular components:
  - Each step (data ingestion, training, evaluation, deployment) should be independent.
- Use config-driven pipelines:
  - Store hyperparameters, paths, and thresholds in YAML or JSON.
  - Allow easy modification without code changes.
- Centralize logging, metrics, and artifacts:
  - Track outputs, logs, and error messages for each task.
- Design pipelines for idempotency:
  - Rerunning the same step multiple times should not cause inconsistent results.
- Monitor task performance:
  - Track metrics like latency, memory usage, retry counts.
  - Optimize slow or failing steps based on monitoring insights.


### 🛠️ **Tools Introduced**

| Category | Tools |
|----------|-------|
| Orchestration | Apache Airflow, Prefect, Kubeflow Pipelines |
| Visualization | Airflow DAG UI, Prefect Orion UI, Kubeflow UI |
| Code Modularity | Python tasks/functions, Docker containers, YAML/JSON configs |
| Monitoring & Logging | Airflow logs, Prefect CLI/UI logs, KFP metadata tracking |

## ✅ **Phase Completion Goals**

At the end of Phase 4, students should:
- Understand the need for robust ML pipelines and the limitations of ad-hoc scripts.
- Be able to design and define DAG-based workflows.
- Build simple ML pipelines using Airflow or Prefect.
- Understand when to choose Kubeflow for advanced orchestration.
- Apply best practices for maintainable, scalable, and observable ML pipelines.