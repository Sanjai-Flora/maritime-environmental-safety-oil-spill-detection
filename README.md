# Maritime Environmental Safety: Advanced Oil Spill Detection through AIS and Remote Sensing

![Status](https://img.shields.io/badge/Status-Prototype-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-yellow)
![Framework](https://img.shields.io/badge/Flask-Web%20App-green)
![AI](https://img.shields.io/badge/Model-U--Net%20%7C%20TensorFlow-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## 📌 Problem Statement
**Detecting oil spills at marine environment using Automatic Identification System (AIS) and satellite datasets.**

Marine oil spills pose a critical threat to ocean ecosystems, often going undetected until significant damage occurs. Traditional monitoring is manual and reactive. This project aims to automate detection by combining **Automatic Identification System (AIS)** data with **Deep Learning analysis of Satellite Imagery** to identify spills and correlate them with vessel traffic.

## 📖 Project Overview
This application serves as a centralized **Maritime Safety Dashboard**. It integrates historical data analysis with real-time AI inference to provide a comprehensive monitoring tool.

The system allows maritime authorities to:
1.  **Monitor Vessel Traffic:** Visualize ship movements and identify suspicious behavior.
2.  **Detect Oil Spills:** Upload satellite imagery (SAR) to a U-Net model that segments oil spills with pixel-level accuracy.
3.  **Analyze Anomalies:** Filter and track vessel anomalies (speed violations, course deviations) that often correlate with illegal dumping.

## 🚀 Key Features

### 1. AI-Powered Oil Spill Detection
*   Utilizes a **U-Net Convolutional Neural Network (CNN)** trained on **Sentinel-1 SAR** imagery.
*   Performs semantic segmentation to classify pixels into 5 categories: *Oil Spill, Look-alikes, Ships, Land, and Sea Surface*.
*   Generates color-coded masks for immediate visual analysis.

### 2. AIS Data & Vessel Tracking
*   Interactive maps powered by **Leaflet.js** and **OpenSeaMap**.
*   Visualizes vessel types (Cargo, Tanker, Military) with specific icons.
*   Provides detailed ship metadata (Speed, Destination, ID) on click.

### 3. Anomaly Detection Module
*   Analyzes historical logs to flag high-risk events.
*   Filters anomalies by type: *Speed Anomaly, Course Deviation, AIS Gap, Zone Violation*.
*   Helps authorities correlate spill locations with potential suspect vessels.

### 4. Secure & User-Friendly Interface
*   **Authentication:** Secure Login/Register system using **Argon2** password hashing.
*   **Security:** Brute-force protection (lockout after 3 failed attempts).
*   **Theme:** Fully responsive UI with toggleable **Dark/Light modes**.

## 📊 Data Architecture & Methodology

> **Note on Data Sources:** This project functions as a High-Fidelity Prototype.

*   **Vessel Data (AIS):** Sourced from **MarineTraffic**. We utilize verified historical datasets stored in local JSON format. This simulation ensures reliability during demonstrations and avoids the prohibitive costs of real-time commercial API feeds.
*   **Satellite Imagery:** We utilize **Sentinel-1 Synthetic Aperture Radar (SAR)** images for the AI model, as SAR can detect oil textures day or night, through clouds.
*   **Oil Spill Records:** Historical spill data is used to map "High Risk" zones and visualize past incidents.

## 🛠️ Technology Stack

| Component | Technology |
| :--- | :--- |
| **Backend** | Python, Flask, Werkzeug |
| **Frontend** | HTML5, CSS3, JavaScript (ES6) |
| **Mapping** | Leaflet.js, OpenSeaMap, Esri Satellite Layer |
| **AI / ML** | TensorFlow, Keras, U-Net Architecture |
| **Image Processing** | NumPy, Pillow (PIL), Matplotlib |
| **Security** | Argon2 Hashing, Flask-Session |

## 👨‍💻 Contributors

| Name | Role | Responsibilities |
| :--- | :--- | :--- |
| **Sanjai A** | **Team Lead** & Backend Dev | System Architecture, Flask Integration, Map Logic |
| **Yuvasri S** | Full Stack Developer | UI/UX Design, Frontend Implementation, Dashboard |
| **Vasanth D** | Backend Developer | Authentication, Session Management, Database Logic |
| **Suganya E** | ML Engineer | U-Net Model Training, Image Preprocessing, Mask Generation |

## ⚙️ Installation & Setup

Follow these steps to run the project locally.

### Prerequisites
*   Python 3.8 or higher installed.
*   Pip (Python Package Installer).

### Steps

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/Sanjai-Flora/maritime-environmental-safety-oil-spill-detection.git
    cd maritime-environmental-safety-oil-spill-detection
    ```

2.  **Create a Virtual Environment**
    ```bash
    python -m venv venv
    # Windows:
    venv\Scripts\activate
    # Mac/Linux:
    source venv/bin/activate
    ```

3.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Application**
    ```bash
    python app.py
    ```

5.  **Access the Dashboard**
    Open your browser and navigate to: `http://127.0.0.1:5039`

## 🔮 Future Scope
*   **Live API Integration:** Replacing JSON simulations with live WebSockets from MarineTraffic.
*   **Cloud Deployment:** Hosting the U-Net model on AWS SageMaker for faster inference.
*   **Automated Alerts:** Integrating Email/SMS Twilio APIs to alert authorities immediately upon detection.

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
