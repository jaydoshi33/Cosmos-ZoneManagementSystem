# 🛜 COSMOS ZMS (Zone Management System)

A comprehensive Zone Management System designed for advancing efficient spectrum sharing and monitoring in NYC/Manhattan. This project consists of a modern React-based frontend and a Python-based backend API for processing SCM (Spectrum Consumption Model) data.

💰 This project is funded by the National Science Foundation(NSF), and being developed in collaboration with **Columbia University**, **Princeton University**, **Syracuse University**, **Rutgers University** and the **NOAA**.

## 💻 Project UI
### Home Page
![Home Page](./ss/Screenshot%202025-09-19%20154219.png)

### Functionalities of the ZMS
![Functionalities of the ZMS](./ss/Screenshot%202025-09-19%20154706.png)

### Upload new Spectrum Consumption Model XML
![Upload new Spectrum Consumption Model XML](./ss/Screenshot%202025-09-19%20154258.png)

### SCM Creation from UI
![Create new SCM-1](./ss/Screenshot%202025-09-19%20155714.png)
![Create new SCM-2](./ss/Screenshot%202025-09-19%20155906.png)
![Create new SCM-3](./ss/Screenshot%202025-09-19%20155926.png)
![Create new SCM-4](./ss/Screenshot%202025-09-19%20155954.png)

### Search and filter SCMs based on the user defined criteria
![Search and Filter SCMs](./ss/Screenshot%202025-09-19%20154347.png)

### Interference Alarm Dashboard(triggers when compatibility test fails)
![Interference Alarm Dashboard](./ss/Screenshot%202025-09-19%20160106.png)

### Search SCMs to add to the Compatibility Test List
![Search SCMs to add to the Compatibility Test List](./ss/Screenshot%202025-09-19%20154621.png)

## 📋 Project Structure

```
.
├── SCM-Processing/       # Backend services for SCM data processing
│   ├── scm-db-gateway/   # Database gateway service (v2 API)
│   ├── scmapi.py         # Main SCM API implementation
│   ├── writer_scm.py     # SCM data writer
│   ├── reader_scm.py     # SCM data reader
│   └── requirements.txt  # Python dependencies
├── frontend-app/         # Frontend application
│   └── cosmoszms/        # COSMOS ZMS React application
│       ├── public/       # Static files
│       └── src/          # React source code
├── k8s/                  # Kubernetes configuration files
└── scm_api_files/        # SCM API definition files
```

## ✅ Prerequisites

- Python 3.8+
- Node.js 16+
- PostgreSQL 12+
- Docker (optional, for containerized deployment)

## Getting Started

### Backend Setup

1. Backend code is inside the SCM-Processing directory. It contains a dockerfile to run it as a container in an isolated environment.
2. The required libraries will be dynamically installed. The kubernetes manifest takes care of configuring database access.
3. Ingress takes care of request routing to the service responsible.
4. Persistent volumes are created on the cluster, which are backed by a shared NFS volume.

### Frontend Setup

1. Frontend application is deployed as a separate container on the cluster.
2. The frontend app sends request to the backend, and ingress routes the request to the appropriate service.


## 🛠️ Technologies Used

### 🗄️ Backend
- Python 3.8+
- FastAPI
- SQLAlchemy
- PostgreSQL
- Uvicorn

### 💻 Frontend
- React 19
- TypeScript
- Material-UI (MUI)
- Redux (for state management)
- Axios (for API calls)
- Recharts (for data visualization)
