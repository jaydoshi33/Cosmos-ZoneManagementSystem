# COSMOS ZMS (Zone Management System)

A comprehensive Zone Management System designed for efficient supply chain management and monitoring. This project consists of a modern React-based frontend and a Python-based backend API for processing SCM (Supply Chain Management) data.

This project is funded by the National Science Foundation(NSF), and being developed in collaboration with Syracuse University, Columbia University, Rutgers University, Princeton University and the NOAA.

## Project UI
![Home Page](./ss/Screenshot%202025-09-19%20154219.png)

## Project Structure

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

## Prerequisites

- Python 3.8+
- Node.js 16+
- PostgreSQL 12+
- Docker (optional, for containerized deployment)

## Getting Started

### Backend Setup

1. Navigate to the SCM-Processing directory:
   ```bash
   cd SCM-Processing
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: .\venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your database credentials
   ```

5. Initialize the database:
   ```bash
   python setup_database.py
   ```

6. Start the SCM API server:
   ```bash
   uvicorn scmapi:app --reload --host 0.0.0.0 --port 8000
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend-app/cosmoszms/frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```
   The application will be available at `http://localhost:3000`


## Deployment

### Docker

You can deploy the application using Docker Compose:

```bash
docker-compose up --build
```

### Kubernetes

Kubernetes deployment configurations are available in the `k8s/` directory.

## Technologies Used

### Backend
- Python 3.8+
- FastAPI
- SQLAlchemy
- PostgreSQL
- Uvicorn

### Frontend
- React 19
- TypeScript
- Material-UI (MUI)
- Redux (for state management)
- Axios (for API calls)
- Recharts (for data visualization)


This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, please open an issue in the GitHub repository.
