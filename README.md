# 7ARTH - CyberSecurity Graduation Project

![Python](https://img.shields.io/badge/Python-3.9-blue)
![Flask](https://img.shields.io/badge/Flask-2.1-green)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.11-orange)
![PyTorch](https://img.shields.io/badge/PyTorch-1.10-red)

> 7ARTH (أرض) - Protecting Your Digital Battlefield

## 📋 Overview

A comprehensive **Intrusion Detection System (IDS)** graduation project combining **Machine Learning**, **Deep Learning**, and **Real-time Network Analysis**. The project consists of **7 sub-systems** covering different aspects of cybersecurity threat detection.

## 🏗️ Project Structure

```
7ARTH-Graduation-Project/
│
├── Real-time-IDS-master/            # MAIN: Real-time packet sniffing IDS
│   ├── application.py               # Flask + SocketIO web app
│   ├── flow/                        # Flow engine (Flow.py, PacketInfo.py)
│   ├── models/                      # Trained models (RF + Autoencoder)
│   ├── templates/                   # Web UI (index.html, detail.html)
│   └── static/                      # CSS, JS, images
│
├── Network-Intrusion-Detection-     # Web-based IDS (NSL-KDD)
│   System-master/
│   ├── app.py                       # Flask web app
│   ├── model.pkl                    # Trained classifier
│   └── NSL_Dataset/                 # NSL-KDD dataset
│
├── APT_Detect/                      # Advanced Persistent Threat Detection
│   ├── code/Untitled-2.ipynb        # PyTorch training notebook
│   ├── data/flowFeatures.csv        # 1.67M flows dataset
│   └── model/                       # Trained model (PyTorch)
│
└── 7ARTH/                           # Multi-component security suite
    ├── attack_detect/               # UNSW-NB15 - 10 ML/DL models
    │   ├── code/                    # Training notebooks
    │   ├── data/                    # UNSW-NB15 dataset
    │   └── model/                   # 10 trained models
    │
    ├── IOT/                         # IoT Intrusion Detection
    │   ├── Auto_Encoder_detection/  # QAE model + TFLite variants
    │   ├── Quantam_anomly_detection/ # Optuna-optimized QAE
    │   └── paper_code/             # Research implementation
    │
    ├── ransomware_detect/           # Memory Malware Detection
    │   ├── data/                    # Obfuscated-MalMem2022 dataset
    │   └── model/knn_gs.pickle      # kNN + GridSearch model
    │
    └── url/                         # Malicious URL Detection
        ├── data/                    # malicious_phish dataset
        └── model/                   # RF + XGBoost models
```

## 🔧 Technologies

| Technology | Usage |
|-----------|-------|
| **Python 3.9** | Core language |
| **Flask 2.1** | Web framework |
| **SocketIO** | Real-time WebSocket communication |
| **Scapy 2.4.5** | Packet capture and analysis |
| **Npcap 1.71** | Windows packet capture driver |
| **scikit-learn** | ML models (RF, kNN, DT, etc.) |
| **TensorFlow 2.11** | Autoencoder (anomaly detection) |
| **PyTorch** | APT detection neural network |
| **XGBoost / LightGBM** | Gradient boosting models |
| **TensorFlow Lite** | IoT edge deployment |
| **Optuna** | Hyperparameter optimization |
| **LIME** | Model explainability |
| **Plotly** | Interactive visualizations |
| **psutil** | Process-to-port mapping |
| **Joblib / Dill** | Model serialization |

## 🎯 What Each Sub-System Does

### 1. Real-time-IDS-master (Main System)
- **Live packet capture** using Scapy
- **Bidirectional flow tracking** (Fwd + Bwd packets)
- **39 flow features extraction** (IAT, packet lengths, flags, window size, etc.)
- **Dual classification**: Random Forest (known attacks) + Autoencoder (anomaly detection)
- **Risk scoring** (Very High → Minimal)
- **LIME explanations** for predictions
- **IP geolocation** (flag icons by country)
- **Real-time web dashboard** via SocketIO

### 2. Network-Intrusion-Detection-System-master
- Flask web form for manual feature input
- NSL-KDD dataset (41 features)
- 5-Class classification: Normal, DOS, PROBE, R2L, U2R
- JSON API endpoint for programmatic access
- Docker + Heroku deployable

### 3. APT_Detect
- PyTorch neural network (81 → 64 → 32 → 1)
- CICIDS flow features dataset (1.67M rows)
- Binary classification: BENIGN vs APT
- Feature scaling + label encoding

### 4. 7ARTH/attack_detect
- 10 ML/DL models comparison on UNSW-NB15
- Models: LR, kNN, DT, RF, ET, GB, MLP, GRU, LSTM, XGBoost
- L1 regularization for feature selection (PyTorch)

### 5. 7ARTH/IOT
- Quantized Autoencoder (QAE) for IoT devices
- TensorFlow Lite optimization: Pruning, Clustering, Integer Quantization
- Optuna hyperparameter tuning
- Edge-deployable .tflite models

### 6. 7ARTH/ransomware_detect
- Memory dump malware detection
- Obfuscated-MalMem2022 dataset
- kNN + GridSearchCV optimization

### 7. 7ARTH/url
- Malicious/Phishing URL detection
- Random Forest + XGBoost models

## 🚀 How to Run

### Prerequisites
```bash
# Windows only! (Requires Npcap)
# Install Npcap 1.71: https://npcap.com/dist/npcap-1.71.exe
# Python 3.9: https://www.python.org/downloads/release/python-3913/
```

### Real-time-IDS (Main System)
```bash
cd Real-time-IDS-master
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
python application.py
# Open http://localhost:5000
```

### Network-Intrusion-Detection-System
```bash
cd Network-Intrusion-Detection-System-master
pip install -r requirements.txt # or: flask, joblib, scikit-learn, numpy
python app.py
# Open http://localhost:5000
```

## 👥 Team

Graduation Project - Cybersecurity & AI

---

## 📄 License

MIT License - This project is for educational purposes.

---

## 🔗 Links

- [CICIDS 2018 Dataset](https://www.unb.ca/cic/datasets/)
- [NSL-KDD Dataset](https://www.unb.ca/cic/datasets/nsl.html)
- [UNSW-NB15 Dataset](https://research.unsw.edu.au/projects/unsw-nb15-dataset)
