# 🚀 MockMate AI Ecosystem

Welcome to the central hub for **MockMate AI**, a precision-engineered platform for technical interview mastery. To maintain architectural integrity, this project is divided into two specialized repositories:

## 📊 Project Dashboard

| Component | Repository Link | Primary Tech Stack | Key Responsibility |
| :--- | :--- | :--- | :--- |
| **Frontend** | [**View Source ↗**](https://github.com/Pranjall-Gupta/MockMate-AI-frontend) | React 18, TS, Tailwind | Glass-morphism UI & Voice Analysis |
| **Backend** | [**View Source ↗**](https://github.com/Pranjall-Gupta/MockMate-AI-backend) | Java 21, Spring Boot | AI Orchestration & JWT Security |
| **Live Demo** | [**Launch App 🚀**](https://mock-mate-ai-delta.vercel.app) | Vercel / Heroku | Immersive User Experience |

---

## 🏗️ System Architecture

<p align="center"><img width="700" alt="system-architecture" src="https://github.com/user-attachments/assets/b81786a0-4c88-4bd7-9c83-f2091a7b3ad1" /></p>

The platform follows a decoupled micro-services-oriented architecture:
* **Client:** Vite-powered React SPA with glass-morphism UI.
* **API Gateway:** Secure Spring Boot REST API with JWT-based authentication.
* **AI Layer:** Multi-modal integration using Azure Speech Service and Azure OpenAI (GPT-4o).

---

## ⚡ Getting Started & Setup Guide
Since the frontend client and the backend API gateway are decoupled, follow the instructions below to set up both services on your local environment.
### 📋 Prerequisites
Ensure you have the following installed on your machine:
* **Node.js** (v18 or higher) & **npm** (or Bun)
* **Java Development Kit (JDK) 21**
* **Maven** (configured in path or using the provided `./mvnw` wrapper)
* A **MongoDB Atlas** database cluster (or local MongoDB server)
* **Azure Cognitive Services** account with keys for:
  * Azure OpenAI Service (with a deployed GPT-4o model)
  * Azure AI Speech Service
    
---

### 🟢 1. Backend Setup (`MockMate-AI-backend`)
The backend is built with Spring Boot 3.5 and handles core database persistence, security, and AI service orchestrations.
#### A. Navigate to the Backend Folder
If you have cloned the unified mono-repo, navigate to the `backend` folder. Otherwise, clone the backend repository:
```bash
git clone https://github.com/Pranjall-Gupta/MockMate-AI-backend.git
cd MockMate-AI-backend
```

#### B. Environment Configuration
The backend reads secret keys from system environment variables. You must set these variables or configure them in your local environment.

Create a  `.env` file or export the following variables in your terminal:
```bash
# Azure OpenAI Credentials
AZURE_OPENAI_KEY="your-azure-openai-api-key"
AZURE_OPENAI_ENDPOINT="https://your-resource-name.openai.azure.com/"
AZURE_OPENAI_DEPLOYMENT="your-gpt-4o-deployment-name"

# Azure AI Speech Credentials
AZURE_SPEECH_KEY="your-azure-speech-api-key"
AZURE_SPEECH_REGION="your-speech-service-region" # e.g. eastus

# Database Credentials
MONGODB_URI="mongodb+srv://<username>:<password>@<cluster>.mongodb.net/?retryWrites=true&w=majority"

# Security & Authentication (Google OAuth)
GOOGLE_CLIENT_ID="your-google-oauth-client-id"
GOOGLE_CLIENT_SECRET="your-google-oauth-client-secret"
FRONTEND_URL="http://localhost:5173" # Local Vite frontend URL
```
> [!NOTE]
> If configuring via IDE (like IntelliJ IDEA or VS Code), you can load these environment variables directly into the Run/Debug Configuration.


#### C. Build & Run
Run the Spring Boot development server on default port 8081:

```bash

# Using Maven wrapper (Windows)
.\mvnw.cmd spring-boot:run
# Using Maven wrapper (Linux/macOS)
./mvnw spring-boot:run
```
The backend server will start and listen at http://localhost:8081.

---

 ### 🔵 2. Frontend Setup (MockMate-AI-frontend)
The frontend is a lightweight, Vite-powered React single page application (SPA) featuring premium glassmorphism styling and custom animations.

#### A. Navigate to the Frontend Folder
Navigate to the `frontend` folder, or clone the frontend repository:

```bash
git clone https://github.com/Pranjall-Gupta/MockMate-AI-frontend.git
cd MockMate-AI-frontend
```
#### B. Environment Configuration
Create a `.env.local` file in the root of the frontend folder and specify the base API endpoint pointing to your backend gateway:

```env
VITE_API_BASE_URL=http://localhost:8081/api
```

### C. Install & Run
Install project dependencies and start the local development server:

```bash
# Install dependencies
npm install
# Start Vite dev server
npm run dev
```
The client application will start running, usually at `http://localhost:5173`. Open this URL in your browser to interact with MockMate AI!

---

### 🤝 Contributing Guidelines
We welcome contributions from the community to help make MockMate AI even more robust and comprehensive! To contribute:

- Fork the target repository (Frontend or Backend).
- Create a new feature branch (git checkout -b feature/amazing-feature).
- Commit your changes with clear, descriptive commit messages (git commit -m 'Add amazing new feature').
- Push to the branch (git push origin feature/amazing-feature).
- Open a Pull Request explaining your implementation details and testing coverage.
  
For major architecture proposals or UI redesigns, please open an issue first to discuss what you would like to change.

---
### 📄 License & Attribution
This project is licensed under the MIT License - see the LICENSE file for details.

Developed with 💖 by Pranjal Gupta as part of the Microsoft IEP Capstone Project, pioneering the intersection of generative artificial intelligence and high-quality technical education.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
