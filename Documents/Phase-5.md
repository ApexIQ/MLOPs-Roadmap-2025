# 📘 **Phase 5: Model Packaging, Deployment & Serving**

## 🎯 **Phase Objective**
Learn how to package trained models into deployable assets, expose them through APIs, containerize them with Docker, and understand options for production-grade serving at scale.

## 🧠 **Topics to Cover**

### **From Trained Model to Production Asset**

- Understand what happens after training is complete:
  - Moving from `.pkl` or `.pt` files to production-ready formats.
- Learn about different model formats:
  - **Pickle**, **Joblib** (Python-based serialization)
  - **ONNX** (open standard for model portability)
  - **TensorFlow SavedModel**, **TorchScript** (deep learning models)
- Requirements for production-ready models:
  - **Reproducibility** (same outputs across environments)
  - **Versioning** (track which model version is deployed)
  - **Lightweight Packaging** (optimize model size and load time)
- Understand security risks:
  - Pickle loading can execute arbitrary code if files are untrusted.
  - Use safe loading practices and signed artifacts where possible.

### **Serving with FastAPI or Flask**

- Creating inference scripts:
  - Set up a simple API endpoint to receive input and return predictions.
- Structuring APIs:
  - Define **POST** endpoints for sending input data.
  - Define **GET** endpoints for health checks, status reporting.
- Parsing payloads:
  - Accept input in formats like JSON, CSV, or images.
  - Validate inputs for required fields and formats.
- Returning model outputs:
  - Predicted values
  - Probabilities
  - Errors or validation feedback

> *Students should implement a sample FastAPI server serving an ML model locally.*

### **Batch vs Real-Time Inference**

- Differences between serving types:
  - **Real-Time Inference**: Immediate predictions, e.g., chatbots, fraud detection.
  - **Batch Inference**: Predict over large datasets at scheduled intervals, e.g., churn predictions.
- Key concerns:
  - **Performance**: Inference latency must meet SLAs (Service Level Agreements).
  - **Scaling**: Handle thousands of requests simultaneously.
  - **API Rate-limiting**: Control incoming request rates to protect services.
  - **Queuing & Caching**: Use background queues or cache frequent predictions to reduce load.

### **Model Packaging with Docker**

- Why containerize ML models:
  - Ensure environment consistency across dev, test, and prod.
  - Bundle dependencies with the model for portability.
- Basics of writing a Dockerfile:
  - Set the base image (e.g., `python:3.9`)
  - Install requirements (`requirements.txt`)
  - Expose necessary ports (e.g., `8000` for FastAPI)
  - Define entrypoints (e.g., `CMD ["python", "app.py"]`)
- Building and testing Docker containers:
  - `docker build -t model-server .`
  - `docker run -p 8000:8000 model-server`
- Publishing images:
  - Tag images correctly (versioning).
  - Push to Docker Hub or a private container registry.

### **Serving with Model Servers**

- Introduction to specialized model servers:
  - **TensorFlow Serving**: Optimized serving for TensorFlow models.
  - **TorchServe**: Optimized serving for PyTorch models.
  - **MLflow Models (serve command)**: Serve any MLflow-logged model easily.
- Pros and Cons:
  - Model servers are optimized for performance and monitoring but may be more rigid compared to custom APIs.
- Monitoring options:
  - Integrate Prometheus or custom loggers to monitor latency, throughput, and failures.

> *Students should explore serving a model using TensorFlow Serving or MLflow serve.*

### **Deploying in the Wild (Preview)**

- Local Deployment:
  - Serve models locally using Docker, FastAPI, or Streamlit for dev/testing.
- Cloud Deployment:
  - Azure ML Endpoints: Managed endpoint hosting.
  - Hugging Face Spaces: Fast demos using Gradio or Streamlit apps.
- Understand basic concepts of production readiness:
  - **Load Testing**: Simulate thousands of concurrent requests.
  - **Model Gateways**: Control versioned access to models.
  - **Endpoint Versioning**: Serve multiple versions for A/B testing or rollback.

### 🛠️ **Tools Introduced**

| Category | Tools |
|----------|-------|
| Model Formats | Pickle, Joblib, ONNX, TensorFlow SavedModel, TorchScript |
| APIs | FastAPI, Flask |
| Containerization | Docker, Docker Hub |
| Model Servers | TensorFlow Serving, TorchServe, MLflow Models |
| Cloud Deployment & Demos | Streamlit Cloud, Hugging Face Spaces, Azure ML Endpoints |


## ✅ **Phase Completion Goals**

At the end of Phase 5, students should:
- Package trained models into reproducible and portable formats.
- Build an API service for model inference using FastAPI or Flask.
- Containerize the model server using Docker.
- Serve models using lightweight REST APIs or specialized model servers.
- Understand basic deployment options and prepare for production scaling.