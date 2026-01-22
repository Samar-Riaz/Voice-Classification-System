# 🔊 Real-Time Voice Classification System

A deep learning system that classifies audio in real-time to distinguish between human/animal voices and other sounds, designed for gate control automation.

---

## 🎯 Features
- **Real-time processing** (~2.1–2.5s latency)
- **>90% accuracy** across all sound categories
- **Binary classification**: Human/Animal vs Other (weapons, mechanical sounds)
- **Thread-safe control logic** for hardware integration
- **Robust error handling** with fallback mechanisms

---

## 🏗️ Architecture

Audio Input → Capture → Feature Extraction → DNN Model → Control Signal

| Stage | Tool |
|---|---|
| Microphone | SoundDevice |
| Feature Extraction | Librosa (MFCC) |
| Model | TensorFlow |
| Output | Gate Control |

---

## 📊 Model Performance

| Metric | Score |
|--------|-------|
| **Accuracy** | >90% |
| **Precision** | High (minimal false positives) |
| **Recall** | High (minimal false negatives) |
| **Processing Time** | 2.1–2.5s total |

---

## 📁 Dataset
- **Human Voices**: 3,000 samples (various accents/genders)
- **Animal Sounds**: 170 samples (birds, dogs, cats, etc.)
- **Other Sounds**: 463 samples (weapons, mechanical noises)
- **Total**: **3,633 WAV files**

---

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/Samar-Riaz/voice-classification-system.git
cd voice-classification-system

# Install dependencies
pip install -r requirements.txt

# Run real-time classification
python src/inference.py --mode realtime

```

## 🛠️ Tech Stack
- **Python 3.7+**
- **TensorFlow 2.8+** — Deep Learning
- **Librosa 0.9+** — Audio Processing
- **SoundDevice 0.4.5+** — Real-time Audio Capture
- **NumPy & Scikit-learn** — Data Processing

## 📈 Model Details
- **Model Type:** 5-layer Deep Neural Network (DNN)
- **Features:** MFCC, Chroma, Spectral Contrast (**72 total**)
- **Regularization:** Dropout + L2
- **Optimizer:** Adam
- **Loss Function:** Binary Cross-Entropy
- **Training Time:** 10–30 minutes

## 🔧 Key Components
- **Audio Capture:** Non-blocking stream with callback
- **Feature Extraction:** Synchronous processing with error recovery
- **Model Inference:** Loaded once at startup (`.h5` format)
- **Control Logic:** State machine for gate control (**OPEN/CLOSED**)

## 📄 Documentation
Full technical report: `ML Voice Recognition System Report.pdf`
