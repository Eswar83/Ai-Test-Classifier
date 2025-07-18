# Project README

## 🚀 Project Overview

This project demonstrates a full-stack AI-powered text classification system. The backend leverages a fine-tuned `distilbert-base-uncased` model for inference, served via FastAPI. The frontend is built with React and communicates with the backend via REST API. The project is containerized using Docker and orchestrated with Docker Compose.

## 📦 Setup & Run Instructions

### Prerequisites:

* Docker
* Docker Compose

### Steps to Run:

1. Clone the repository:

   ```bash
   git clone <your-repo-url>
   cd <repo-folder>
   ```

2. Start all services:

   ```bash
   docker-compose up --build backend frontend
   ```

   This launches:

   * Backend at: [http://localhost:8000](http://localhost:8000)
   * Frontend at: [http://localhost:3000](http://localhost:3000)

3. To fine-tune the model:

   ```bash
   docker-compose run --rm finetune
   ```

   This will fine-tune the model using `data.jsonl` in the `backend` folder and save the updated model in the `model` directory.

## 🎯 Design Decisions

* **FastAPI** for backend: lightweight and OpenAPI-compatible.
* **React** for frontend: rapid UI development and community support.
* **Docker**: for reproducible environments and ease of deployment.
* **Model Mounting**: The `model/` directory is mounted across both backend and fine-tune containers to share weights seamlessly.

## 🧠 CPU Fine-tune Time (Estimate)

| Epochs | Device | Time (Approx.) |
| ------ | ------ | -------------- |
| 3      | CPU    | 12 mins        |

(Note: This project was only tested on CPU. GPU support was not used.)

## 🔌 API Docs (FastAPI - OpenAPI Spec)

Once backend is running, access full API docs at:

* [http://localhost:8000/docs](http://localhost:8000/docs)

### Sample Endpoints:

* **POST /predict**

  * Input: `{ "text": "your input here" }`
  * Output: `{ "label": "classified_label", "confidence": 0.89 }`

## 📹 Screen Recording

* Watch the project walkthrough (under 3 mins):

  * [🔗 YouTube Link (Unlisted)](https://www.youtube.com/watch?v=YOUR_UNLISTED_LINK)

## ☁️ Deployed Version

* Deployment not done using Vercel. The application was run and tested locally using Docker. For demonstration, backend was exposed using tools like `ngrok` if needed.

## 🐳 Docker Files

* `Dockerfile` for backend and frontend included.
* `docker-compose.yml` provided to orchestrate multi-container setup.

---
