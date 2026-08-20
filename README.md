# 🏥 Development of Healthcare Operations Intelligence Dashboard with Decision Analytics

> **An interactive Business Intelligence and Decision Support System for healthcare operations, developed using Python, Pandas, Plotly, and Streamlit.**

The **Healthcare Operations Intelligence Dashboard** transforms raw hospital operational data into meaningful KPIs, interactive visualizations, alerts, and actionable insights.

It brings together data from **patients, laboratories, pharmacy, ambulance services, staff scheduling, appointments, operation theatres, and emergency departments** into a centralized dashboard designed to help healthcare administrators monitor operational performance and make faster, data-driven decisions.

---

## 📌 Project Overview

Healthcare operations generate large volumes of data across multiple departments. Analyzing these datasets manually can make it difficult to identify operational issues, trends, and areas requiring immediate attention.

This project addresses that challenge by developing a centralized **Healthcare Operations Intelligence Dashboard** that converts raw operational data into decision-oriented analytics.

The system follows the pipeline:

**Raw Healthcare Data → Data Cleaning → KPI Calculation → Interactive Visualization → Decision Analytics → Alerts & Insights**

The dashboard focuses on presenting the most relevant information instead of overwhelming users with unnecessary metrics and visualizations.

---

## 🎯 Objectives

* Centralize healthcare operational data in a single dashboard
* Transform raw Excel data into meaningful analytical insights
* Monitor important healthcare operational KPIs
* Identify potential operational issues through automated alerts
* Analyze trends across different healthcare departments
* Provide interactive filtering and visualizations
* Support faster and more informed administrative decisions
* Implement secure dashboard access through authentication
* Develop a reusable and scalable dashboard architecture

---

## ✨ Key Features

### 🔐 Secure Authentication

* Login required before accessing dashboard pages
* Session-based authentication
* Credentials stored securely using Streamlit Secrets
* Individual dashboard pages protected using an additional access guard
* Sensitive credentials excluded from the GitHub repository

### 📊 Executive Overview

* Curated executive KPIs
* Operational alerts
* Trend analysis
* Revenue analysis
* High-level healthcare performance monitoring
* Centralized data upload functionality

### 👥 Patient Analytics

* Patient demographics
* Hospital admissions
* Billing analysis
* Patient satisfaction
* Hospital visit trends

### 🧪 Laboratory Intelligence

* Test volume analysis
* Laboratory revenue
* Test category distribution
* Technician workload analysis
* Laboratory performance indicators

### 💊 Pharmacy Analytics

* Medicine sales analysis
* Category performance
* Branch-level performance
* Medicine demand intelligence
* Dispensing velocity analysis

> **Note:** The source dataset does not contain a live stock-on-hand field. Therefore, dispensing velocity is used as a practical proxy for identifying fast-moving medicines that may require attention.

### 🚑 Ambulance Monitoring

* Ambulance response time analysis
* Travel time analysis
* Fuel cost monitoring
* Driver workload
* Transportation performance

### 👨‍⚕️ Staff Scheduling

* Staff leave analysis
* Overtime monitoring
* Duty type distribution
* Emergency coverage
* Workforce workload insights

### 📅 Appointment Analytics

* Appointment completion rate
* Cancellation rate
* No-show rate
* Peak appointment hours
* Appointment trends

### 🏥 Operation Theatre Dashboard

* Surgery status
* OT room utilization
* Surgeon workload
* Operational performance indicators

### 🚨 Emergency Monitoring

* Emergency case trends
* Monthly analysis
* Emergency category distribution
* Seasonal patterns
* Heatmap-based analysis

---

## 📈 Decision Analytics

The dashboard is designed around **5–7 decision-relevant KPIs per page** rather than displaying excessive metrics.

Each page includes:

* **Hero KPI** — the primary metric requiring attention
* **Supporting KPIs** — additional operational indicators
* **Alerts** — plain-language warnings generated from calculated metrics
* **Interactive charts** — focused on meaningful comparisons
* **Filters** — available directly within each page

For example:

> **Bed occupancy is at 92% — prepare additional beds.**

This approach transforms numerical data into clear operational information that can support healthcare administrators in making timely decisions.

---

## 🗂️ Project Structure

```text
hospital_dashboard/
│
├── Home.py
│
├── views/
│   ├── Overview.py
│   ├── Patient_Overview.py
│   ├── Laboratory.py
│   ├── Pharmacy.py
│   ├── Ambulance.py
│   ├── Staff_Scheduling.py
│   ├── Appointments.py
│   ├── OT_Dashboard.py
│   └── Emergency_Monitoring.py
│
├── utils/
│   ├── auth.py
│   ├── data_loader.py
│   ├── kpi.py
│   └── styling.py
│
├── data/
│   └── Hospital_Dataset_Complete_Project.xlsx
│
├── .streamlit/
│   ├── config.toml
│   └── secrets.toml.example
│
├── requirements.txt
├── .gitignore
└── README.md
```

### Folder Responsibilities

| Folder/File            | Purpose                                                       |
| ---------------------- | ------------------------------------------------------------- |
| `Home.py`              | Application entry point and login interface                   |
| `views/`               | Individual dashboard pages                                    |
| `utils/auth.py`        | Authentication and page access protection                     |
| `utils/data_loader.py` | Excel loading, cleaning, and caching                          |
| `utils/kpi.py`         | KPI calculations and alert logic                              |
| `utils/styling.py`     | Dashboard design system and reusable UI components            |
| `data/`                | Sample healthcare dataset                                     |
| `.streamlit/`          | Streamlit configuration and secrets template                  |
| `requirements.txt`     | Python dependencies                                           |
| `.gitignore`           | Prevents sensitive and unnecessary files from being committed |

---

## 📋 Dashboard Modules

| Module                   | Data Source                | Main Insights                                   |
| ------------------------ | -------------------------- | ----------------------------------------------- |
| **Overview**             | All datasets               | Executive KPIs, alerts, trends, revenue         |
| **Patient Overview**     | `Hospital_Visits`          | Demographics, admissions, billing, satisfaction |
| **Laboratory**           | `laboratory data`          | Tests, revenue, categories, workload            |
| **Pharmacy**             | `pharmacy data`            | Sales, categories, branches, demand             |
| **Ambulance**            | `Ambulance_Transportation` | Response time, travel time, fuel, workload      |
| **Staff Scheduling**     | `Staff_Scheduling`         | Leave, overtime, duties, coverage               |
| **Appointments**         | `Appointments`             | Completion, cancellation, no-show, peak hours   |
| **OT Dashboard**         | `OT_Dashboard`             | Surgeries, utilization, surgeon workload        |
| **Emergency Monitoring** | `ER_Monitoring_Summary`    | Cases, trends, categories, seasonality          |

---

## 🛠️ Technology Stack

| Technology          | Purpose                                     |
| ------------------- | ------------------------------------------- |
| **Python**          | Core programming language                   |
| **Streamlit**       | Interactive dashboard framework             |
| **Pandas**          | Data cleaning, transformation, and analysis |
| **Plotly**          | Interactive data visualizations             |
| **OpenPyXL**        | Excel file processing                       |
| **Microsoft Excel** | Source healthcare dataset                   |

---

## 🎨 Design System

The dashboard uses a centralized design system implemented in `utils/styling.py`.

### Main UI Components

* Gradient page headers
* KPI cards
* Hero metrics
* Reusable filter bars
* Interactive chart cards
* Consistent section headings
* Custom stroke-based icons
* Responsive dashboard layout
* Soft gradient application background
* Subtle animations
* Color-coded KPI states

The centralized styling system ensures that all dashboard pages maintain a consistent visual identity and user experience.

---

## 🔄 Data Processing Pipeline

```text
Healthcare Excel Workbook
          │
          ▼
     Data Loading
          │
          ▼
    Data Cleaning
          │
          ▼
   Data Aggregation
          │
          ▼
    KPI Calculation
          │
          ▼
 Interactive Charts
          │
          ▼
 Decision Analytics
          │
          ▼
  Alerts & Insights
          │
          ▼
Administrative Decisions
```

---

## 🔐 Authentication

Authentication is required before dashboard access.

The application uses:

* `Home.py` for the login interface
* `utils/auth.py` for page-level access protection
* `.streamlit/secrets.toml` for credential storage

### Demo Credentials

The example configuration contains:

| Username | Password       |
| -------- | -------------- |
| `admin`  | `admin123`     |
| `doctor` | `hospital2026` |

> ⚠️ **Important:** These credentials are provided only for demonstration purposes. Change them before deploying the application publicly.

**Never commit your actual `.streamlit/secrets.toml` file to GitHub.**

---

## 💻 Run the Project Locally

### 1. Clone the Repository

```bash
git clone https://github.com/deepikae1504/Medical_dashboard.git
cd Medical_dashboard
```

### 2. Create a Virtual Environment

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS / Linux:**

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Credentials

**Windows:**

```bash
copy .streamlit\secrets.toml.example .streamlit\secrets.toml
```

**macOS / Linux:**

```bash
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
```

Then edit `secrets.toml` and configure your own username and password.

### 5. Start the Application

```bash
streamlit run Home.py
```

The application will normally be available at:

```text
http://localhost:8501
```

The bundled Excel dataset is loaded automatically when the application starts.

---

## 📂 Using Your Own Healthcare Dataset

The dashboard supports Excel workbooks containing the following exact sheet names:

```text
Hospital_Visits
laboratory data
pharmacy data
Ambulance_Transportation
Staff_Scheduling
Appointments
OT_Dashboard
ER_Monitoring_Summary
```

You can either:

1. Replace the bundled Excel dataset with another compatible workbook, or
2. Upload a workbook through the dashboard's file uploader.

The uploaded dataset is automatically used across the dashboard pages.

---

## ☁️ Deployment

The application can be deployed using **Streamlit Community Cloud**.

### Deployment Steps

1. Push the project to GitHub.
2. Open Streamlit Community Cloud.
3. Create a new application.
4. Select this GitHub repository.
5. Select the required branch.
6. Set the main file to:

```text
Home.py
```

7. Add the contents of your `secrets.toml` through the deployment platform's **Secrets** settings.
8. Deploy the application.

Dependencies are installed automatically using:

```text
requirements.txt
```

### Important

Do **not** upload:

```text
.streamlit/secrets.toml
```

to GitHub.

Only the example configuration should be committed:

```text
.streamlit/secrets.toml.example
```

---

## 🐳 Docker Support

The application can also be containerized using Docker.

```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY . .

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8501

CMD ["streamlit", "run", "Home.py", "--server.address=0.0.0.0"]
```

---

## 🧩 Troubleshooting

| Issue                          | Solution                                                   |
| ------------------------------ | ---------------------------------------------------------- |
| `ModuleNotFoundError`          | Run `pip install -r requirements.txt`                      |
| Blank or old data after upload | Refresh the browser after uploading a new workbook         |
| `No dataset loaded yet`        | Open the Overview page first                               |
| Login fails                    | Check `.streamlit/secrets.toml` and verify the credentials |
| Port already in use            | Run `streamlit run Home.py --server.port 8502`             |
| Dashboard does not start       | Verify Python version and installed dependencies           |

---

## 🚀 Future Enhancements

Potential improvements for future versions include:

* Real-time healthcare database integration
* Role-based access control
* Live bed occupancy monitoring
* Medicine stock-level integration
* Predictive analytics
* Patient admission forecasting
* Emergency demand forecasting
* Automated email and notification alerts
* Advanced anomaly detection
* Healthcare performance benchmarking
* Cloud database integration
* Audit logging
* Enhanced security and encryption

---

## 🌟 Project Highlights

### 1. Decision-Focused KPIs

The dashboard avoids unnecessary metrics and focuses on indicators that support operational decision-making.

### 2. Automated Intelligence

Raw numerical values are converted into plain-language alerts and actionable insights.

### 3. Multi-Department Integration

Multiple healthcare departments are analyzed through one centralized application.

### 4. Secure Architecture

Authentication and secrets management are incorporated instead of placing credentials directly in the source code.

### 5. Interactive Analytics

Users can filter datasets and explore trends through interactive Plotly visualizations.

### 6. Reusable Architecture

Data loading, authentication, KPI calculations, and styling are separated into reusable utility modules.

---

## 🔒 Data & Privacy

This project uses a **sample healthcare dataset for demonstration and development purposes**.

Do not upload real patient information, personally identifiable information (PII), medical records, or other confidential healthcare data to a public repository.

---

## 👩‍💻 Author

### Deepika E

**GitHub:** [@deepikae1504](https://github.com/deepikae1504)

---

## 📄 License

This project is licensed under the **MIT License**.

See the [`LICENSE`](LICENSE) file for details.

---

## 🔎 One-Line Project Summary

**A secure Python/Streamlit healthcare Business Intelligence system that transforms multi-department operational data into curated KPIs, interactive analytics, decision insights, and actionable alerts for faster data-driven decision-making.**
