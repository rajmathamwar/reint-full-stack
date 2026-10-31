# Wind Forecast Monitor

A full-stack wind power forecasting dashboard built using **React, FastAPI, and the Elexon API**. The application monitors historical wind generation forecasts, evaluates forecast accuracy, and provides decision-time analysis through an interactive dashboard.

## 🚀 Features

- **Live Data Integration:** Fetch wind generation and forecast data from the Elexon API.
- **Historical Forecast Analysis:** Track forecasts across different publication times.
- **Forecast Accuracy:** Evaluate predicted wind generation against actual generation.
- **Decision-Time Evaluation:** Analyse forecasts available at specific decision cut-off times.
- **Interactive Dashboard:** Visualize wind generation, forecast performance, and data coverage.
- **Data Quality Monitoring:** Identify missing records and monitor dataset completeness.
- **Synthetic Fallback Mode:** Support demo and offline testing with clearly labelled synthetic data.
- **Docker Deployment:** Containerized application deployment.

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| Frontend | React, JavaScript |
| Backend | Python, FastAPI |
| Data Source | Elexon API |
| Data Processing | Python, Pandas |
| Deployment | Docker, Docker Compose |
| Testing | Pytest |

## 📁 Project Structure

```text
reint-full-stack/
├── backend/
│   ├── app/
│   ├── data/
│   ├── requirements.txt
│   └── requirements-dev.txt
├── frontend/
│   ├── src/
│   └── package.json
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
└── README.md
```

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd reint-full-stack
```

### 2. Backend Setup

```bash
cd backend

python -m venv .venv
```

Activate the virtual environment.

**Windows:**
```bash
.venv\Scripts\activate
```

**Linux / macOS:**
```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements-dev.txt
```

### 3. Refresh Elexon Data

```bash
python -m app.refresh
```

This fetches the required historical generation and forecast data and updates the local snapshot.

### 4. Frontend Setup

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

### 5. Run Backend

From the `backend` directory:

```bash
uvicorn app.main:app --reload
```

## 🐳 Docker Deployment

Build the Docker image:

```bash
docker compose build
```

Start the application:

```bash
docker compose up -d
```

Check running containers:

```bash
docker compose ps
```

Stop the application:

```bash
docker compose down
```

## 🌐 Application URLs

| Service | URL |
|---|---|
| Dashboard | http://localhost:8000 |
| API Health | http://localhost:8000/api/health |
| API Metadata | http://localhost:8000/api/meta |

## 🧪 Testing

Run backend tests:

```bash
cd backend
pytest
```

## 📊 Data Source

This project uses the **Elexon Insights API** to retrieve electricity generation and wind forecast information for Great Britain.

Official API documentation:

https://bmrs.elexon.co.uk/api-documentation

## 🎯 Project Objective

The objective of Wind Forecast Monitor is to provide a reliable way to analyse wind power forecasting performance by comparing historical forecasts with actual generation data.

It helps evaluate forecast accuracy, publication timing, data coverage, and forecast availability at specific decision times.

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.
