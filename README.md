<p align="center">
  <img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/logo.png" width="100" alt="Sehtak AI logo" />
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a2540,50:1565c0,100:42a5f5&height=210&section=header&text=Sehtak%20AI&fontSize=72&fontColor=ffffff&fontAlignY=42&desc=AI-Assisted%20Lung%20Cancer%20Screening%20Platform&descAlignY=66&descColor=e3f2fd&descSize=20" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" />
  <img src="https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" />
  <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Full--Stack-0a2540?style=flat-square" />
  <img src="https://img.shields.io/badge/Roles-Patient%20%C2%B7%20Doctor%20%C2%B7%20Hospital-1565c0?style=flat-square" />
  <img src="https://img.shields.io/badge/AI-Lung%20CT%20Classification-42a5f5?style=flat-square" />
  <img src="https://img.shields.io/badge/Explainability-Grad--CAM-0a2540?style=flat-square" />
</p>

---

## Overview

**Sehtak AI** is a full-stack medical platform that brings artificial intelligence into the lung cancer screening workflow. It connects the three people involved in a diagnosis — the **Patient**, the **Doctor**, and the **Hospital** — around a single chest CT scan.

A scan enters the system, a deep-learning model classifies it across four lung categories, a **Grad-CAM** heatmap shows exactly which region drove the decision, and the case is routed to a licensed doctor for the final medical response.

> The model is built to **support** the physician, not replace them. The final diagnosis always belongs to a licensed doctor.

---

## How the System Works

Sehtak AI is organized around one object — a **scan** — that flows between three roles and the AI engine.

```mermaid
flowchart LR
    P["PATIENT<br/>uploads a CT scan"] --> AI
    H["HOSPITAL<br/>uploads a scan on<br/>behalf of a patient"] --> AI
    AI["AI ENGINE<br/>CLAHE - CNN Ensemble - Grad-CAM"] --> REP["SCAN REPORT<br/>class - confidence<br/>risk - heatmap"]
    REP --> D["DOCTOR<br/>reviews the case"]
    D --> RES["MEDICAL RESPONSE"]
    RES --> VIEW["PATIENT<br/>views AI analysis +<br/>doctor's decision"]
    REP --> VIEW
```

**Lifecycle of a scan**

1. A **patient** uploads a chest CT scan — or a **hospital** uploads it on the patient's behalf when the scan is held on their side.
2. The **AI engine** enhances the image, classifies it, and produces a report: predicted class, confidence, risk level, and a Grad-CAM heatmap.
3. The patient instantly sees the AI analysis and can **request a doctor review**.
4. A **doctor** opens the case — scan, AI summary, and patient medical history — and writes a medical response.
5. The **patient** receives the doctor's decision alongside the AI analysis, and can **book an appointment**.
6. The **hospital** tracks every report's status and assigns doctors to pending scans.

---

## The Patient

A patient signs in, completes a short medical history, uploads a scan, receives an explainable AI analysis, requests a doctor's opinion, and manages appointments.

<table>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/splash.png" width="230" /><br/><sub>1. App Launch</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/login.png" width="230" /><br/><sub>2. Role-Based Login</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/medical-history.png" width="230" /><br/><sub>3. Medical History Setup</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/patient-dashboard.png" width="230" /><br/><sub>4. Patient Dashboard</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/upload-report.png" width="230" /><br/><sub>5. Upload Scan</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/ai-result.png" width="230" /><br/><sub>6. AI Lung Analysis + Grad-CAM</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/select-doctor.png" width="230" /><br/><sub>7. Request Doctor Review</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-response.png" width="230" /><br/><sub>8. Doctor's Response</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/appointments.png" width="230" /><br/><sub>9. Appointments</sub></td>
  </tr>
</table>

The **AI Lung Analysis** screen is the heart of the patient experience — it returns the predicted class, a confidence score, a colour-coded risk level, a Grad-CAM overlay, and clinical recommendations, all under a clear "AI decision-support only" notice.

---

## The Doctor

The doctor signs in, sees prioritized pending cases, reviews each scan together with the AI summary and the patient's medical history, then submits a professional medical response.

<table>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-login.png" width="230" /><br/><sub>1. Doctor Login</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-dashboard.png" width="230" /><br/><sub>2. Doctor Dashboard</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-pending-cases.png" width="230" /><br/><sub>3. Pending Cases</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-case-details.png" width="230" /><br/><sub>4. Case Details + AI Summary</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-response2.png" width="230" /><br/><sub>5. Write Medical Response</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/doctor-profile.png" width="230" /><br/><sub>6. Verified Doctor Profile</sub></td>
  </tr>
</table>

Each case shows the **Grad-CAM overlay**, the AI's predicted class and confidence, the patient's notes, and their medical, family, and allergy history — giving the doctor full context before deciding.

---

## The Hospital

The hospital signs in, uploads scans for patients whose imaging is held on their side, sends them to the AI, assigns doctors to pending scans, and tracks every report end-to-end.

<table>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/hospital-login.png" width="230" /><br/><sub>1. Hospital Login</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/hospital-dashboard.png" width="230" /><br/><sub>2. Hospital Dashboard</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/hospital-upload-scan.png" width="230" /><br/><sub>3. Upload Scan for Patient</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/hospital-reports-status.png" width="230" /><br/><sub>4. Reports Status + Assign Doctors</sub></td>
    <td align="center"><img src="https://github.com/hagerbayoumi11/Sehtak-AI/raw/main/hospital-bookings.png" width="230" /><br/><sub>5. Bookings Management</sub></td>
    <td align="center"></td>
  </tr>
</table>

---

## The AI Engine

The deep-learning module classifies a chest CT scan into four categories — **Adenocarcinoma, Large cell carcinoma, Squamous cell carcinoma, and Normal** — and explains every prediction.

| Stage | What happens |
| --- | --- |
| Image enhancement | CLAHE boosts local contrast on the CT slice |
| Augmentation | Rotations, flips and affine transforms expand the training set |
| Transfer learning | Four CNN backbones fine-tuned: ResNet-50, EfficientNet-B2, DenseNet-121, MobileNet-V3 |
| Two-phase training | Head trained with frozen backbone, then full fine-tuning (AdamW + CosineAnnealingLR) |
| Explainability | Grad-CAM heatmaps trace each prediction to the influential lung region |
| Robust inference | Model ensembling, test-time augmentation, and a confidence threshold for uncertain cases |

---

## Tech Stack

| Layer | Technologies |
| --- | --- |
| Mobile / Web | Flutter |
| Backend API | Node.js, Express, MongoDB, JWT |
| AI Service | Python, PyTorch, Torchvision, OpenCV, Flask |
| Explainability | Grad-CAM |

---

## Disclaimer

Sehtak AI was developed for **academic and research purposes**. It is **not a medical device** and must not be used for real diagnosis or treatment decisions. All AI output is decision-support only; the final diagnosis is made by a licensed physician.

---

## Author

**Hager Bayoumi** — Data Scientist and AI / ML Engineer

<p align="left">
  <a href="https://linkedin.com/in/hagar-mohamed-9bb768261"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://github.com/hagerbayoumi11"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="mailto:hagerbayoumi11@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:42a5f5,50:1565c0,100:0a2540&height=120&section=footer" />
</p>
