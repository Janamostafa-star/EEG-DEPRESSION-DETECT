# 🧠 EEG-Based Depression Detection

> A full-stack mobile health application that detects depression from EEG signals using machine learning — built for accessible, early mental health screening. Achieves **90%+ classification accuracy** on the MODMA dataset.

---

## 📌 Overview

Depression affects over 280 million people globally, yet diagnosis remains largely subjective and inaccessible. This project presents an end-to-end system that analyzes EEG (electroencephalogram) brainwave signals to classify depression, bridging neuroscience and mobile technology into a practical clinical tool.

Built independently as part of the **HSIL Harvard Health Applications Hackathon 2026**, this app demonstrates a complete pipeline from raw EEG signal processing to real-time mobile inference.

---

## 💡 Software Engineering Highlights

- **Full-stack ownership** — Sole developer across mobile, backend, and ML pipeline
- **RESTful API design** — Clean Flask endpoints decoupling frontend from ML logic
- **Modular architecture** — Signal processing, model inference, and app logic are fully separated concerns
- **Cloud-native** — Firebase handles auth, real-time sync, and storage with no custom infra
- **Cross-platform** — Single Flutter codebase targeting both Android and iOS

---

## ✨ Key Features

- 🔬 **EEG Signal Processing** — Applies Random Matrix Theory (RMT) denoising to remove noise artifacts from raw EEG recordings
- 🤖 **ML Classification** — Trained classifier on the MODMA dataset achieving **90%+ accuracy** on held-out test data
- 📱 **Cross-platform Mobile App** — Flutter frontend with clean, intuitive UI for patients and clinicians
- ☁️ **Cloud Backend** — Python/Flask REST API hosted with Firebase for real-time data sync and authentication
- 🔐 **Secure Auth** — Firebase Authentication for user management

---

## 🏗️ Architecture

```
┌─────────────────────┐        ┌──────────────────────┐
│   Flutter Frontend  │ ──────▶│   Python/Flask API   │
│   (Mobile App)      │        │   (Backend Server)   │
└─────────────────────┘        └──────────┬───────────┘
                                           │
                                ┌──────────▼───────────┐
                                │   ML Pipeline        │
                                │  ┌────────────────┐  │
                                │  │ RMT Denoiser   │  │
                                │  └───────┬────────┘  │
                                │  ┌───────▼────────┐  │
                                │  │   Classifier   │  │
                                │  └───────┬────────┘  │
                                │  ┌───────▼────────┐  │
                                │  │  Prediction    │  │
                                │  └────────────────┘  │
                                └──────────────────────┘
                                           │
                                ┌──────────▼───────────┐
                                │   Firebase           │
                                │  (Auth + Database)   │
                                └──────────────────────┘
```

---

## 🧰 Tech Stack

| Layer | Technology |
|---|---|
| Mobile Frontend | Flutter (Dart) |
| Backend API | Python, Flask |
| ML & Signal Processing | scikit-learn, NumPy, SciPy |
| EEG Denoising | Random Matrix Theory (RMT) |
| Database & Auth | Firebase Firestore, Firebase Auth |
| Dataset | MODMA (Multi-modal Open Dataset for Mental-disorder Analysis) |

---

## 📊 Dataset

The model is trained on the **[MODMA Dataset](http://modma.lzu.edu.cn/data/index/)** — a publicly available, research-grade EEG dataset specifically curated for mental disorder analysis, including depression classification.

- EEG recordings from clinically diagnosed depressed patients and healthy controls
- Preprocessed using RMT-based denoising to isolate genuine neural signal from noise

---

## 🚀 Getting Started

### Prerequisites

- Flutter SDK ≥ 3.0
- Python ≥ 3.9
- Firebase project with Firestore & Authentication enabled

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/Janamostafa-star/EEG-DEPRESSION-DETECT.git
cd EEG-DEPRESSION-DETECT

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the Flask server
python app.py
```

### Flutter Setup

```bash
# Navigate to Flutter app directory
cd flutter_app

# Install dependencies
flutter pub get

# Run on device/emulator
flutter run
```

> ⚠️ Add your own `google-services.json` (Android) and `GoogleService-Info.plist` (iOS) from your Firebase console. These are excluded from the repo for security.

---

## 📁 Project Structure

```
EEG-DEPRESSION-DETECT/
├── flutter_app/          # Flutter mobile application
│   ├── lib/
│   └── pubspec.yaml
├── backend/              # Python Flask API
│   ├── app.py
│   ├── model/            # Trained ML model
│   └── requirements.txt
├── ml/                   # ML training & preprocessing scripts
│   ├── preprocess.py     # RMT denoising pipeline
│   └── train.py          # Model training
└── README.md
```

---

## 🔭 Future Work

- [ ] Improve model accuracy with deeper neural architectures (CNN/LSTM on raw EEG)
- [ ] Add real-time EEG streaming via Bluetooth headset integration
- [ ] Expand dataset with local Egyptian patient cohort (Egypt Vision 2030 alignment)
- [ ] Pursue regulatory pathway for clinical pilot deployment

---

## 👩‍💻 Author

**Jana Mostafa**
Biomedical Engineering Student — AUC Cairo
Built for the HSIL Harvard Health Applications Hackathon 2026

---

## 📄 License

This project is intended for academic and research purposes only. Not for clinical use without regulatory approval.
