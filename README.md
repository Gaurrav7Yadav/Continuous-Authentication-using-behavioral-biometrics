# Behavioral Biometrics for Continuous Authentication

A secure, machine learning–driven system that continuously authenticates users based on their behavioral patterns (e.g., keystroke dynamics, mouse movements), ensuring real-time protection throughout a session.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Key Features](#key-features)
- [Technical Overview](#technical-overview)
  - [System Architecture](#system-architecture)
  - [Machine Learning Models](#machine-learning-models)
  - [Technical Specifications](#technical-specifications)
- [Methodology and Implementation](#methodology-and-implementation)
  - [Data Collection & Preprocessing](#data-collection--preprocessing)
  - [Model Training and Evaluation](#model-training-and-evaluation)
  - [Real-Time Monitoring and Response](#real-time-monitoring-and-response)
- [Project Demonstration and Results](#project-demonstration-and-results)
- [Challenges and Learnings](#challenges-and-learnings)
  - [Technical Challenges Overcome](#technical-challenges-overcome)
  - [Performance Metrics Achieved](#performance-metrics-achieved)
  - [User Feedback](#user-feedback)
  - [Technical Limitations](#technical-limitations)
- [Personal Technical Growth and Future Roadmap](#personal-technical-growth-and-future-roadmap)
  - [Key Learnings](#key-learnings)
  - [Planned Features and Future Improvements](#planned-features-and-future-improvements)
  - [Scalability Considerations](#scalability-considerations)
  - [Model Improvements and Research Directions](#model-improvements-and-research-directions)
- [Project Timeline](#project-timeline)
- [Installation and Usage](#installation-and-usage)



---

## Project Overview

This project implements a **continuous authentication system** utilizing behavioral biometrics—such as keystroke dynamics and mouse movement patterns—to verify user identity in real-time. It leverages machine learning models (including Random Forest classifiers and Euclidean distance algorithms) for fast anomaly detection, ensuring that the user interacting with a system remains authenticated throughout the session.

*Images below are representative visualizations extracted from the supporting documentation (please update paths accordingly):*

<img width="771" alt="Screenshot 2025-04-16 at 7 31 28 PM" src="https://github.com/user-attachments/assets/66d714bd-41f1-4183-8b89-3078362f495f" />

*Figure: System Architecture Diagram*

<img width="609" alt="Screenshot 2025-04-16 at 7 31 07 PM" src="https://github.com/user-attachments/assets/03927f46-72b2-4eec-9797-33f24e8829f3" />

*Figure: Data Flow Diagram*

---

## Motivation

- **Security Gap in Traditional Methods:**  
  Static authentication (passwords, fingerprints) only validates identity at login. If a device is left unattended, the system is vulnerable to session hijacking or unauthorized access.

- **Continuous Security:**  
  By analyzing behavioral patterns continuously, the system ensures protection throughout the session, making it extremely useful in high-security sectors like online banking, remote work, and healthcare.

- **Cost Efficiency:**  
  The project uses standard hardware without the need for specialized biometric sensors, reducing implementation cost and complexity.

---

## Key Features

- **Continuous Authentication:**  
  Monitors user interactions (keystroke dynamics, mouse movements) in real time.

- **Real-Time Anomaly Detection:**  
  Uses machine learning for immediate identification of deviations from user behavioral baselines.

- **Robust Data Security:**  
  Implements AES encryption for data-at-rest and TLS for data-in-transit, along with anonymization practices for user data.

- **Modular Design:**  
  System components (data collection, processing, alerting) are decoupled to support scalability and maintainability.

- **User-Friendly:**  
  Operates unobtrusively, prompting re-authentication only when necessary, without disrupting user workflows.

---

## Technical Overview

### System Architecture

The architecture is divided into several layers:

1. **Data Collection Layer:**  
   - Captures behavioral data (keystroke timings, mouse trajectories) via lightweight client-side applications.
   
2. **Processing Layer:**  
   - Preprocesses data, normalizes metrics, and feeds data into machine learning models.
   
3. **Machine Learning Engine:**  
   - Uses a Random Forest Classifier and Euclidean distance measures to compare real-time data against stored user baselines.
   
4. **Response Module:**  
   - Initiates alerts, triggers re-authentication, or terminates sessions based on anomaly detection.
   
5. **Secure Storage:**  
   - Maintains encrypted and anonymized user profiles and logs for audit and retraining purposes.

*Additional diagrams:*

- **Use Case Diagram:**
<img width="761" alt="Screenshot 2025-04-16 at 7 34 26 PM" src="https://github.com/user-attachments/assets/0e92bf35-37a3-4564-9fd6-6b0b1947607c" />



- **Sequence Diagram:**  
 <img width="775" alt="Screenshot 2025-04-16 at 7 32 42 PM" src="https://github.com/user-attachments/assets/50af3d51-edc1-4e0c-ac57-26995831bebe" />


### Machine Learning Models

- **Random Forest Classifier:**  
  - An ensemble approach that handles high-dimensional input data and reduces overfitting.
  
- **Euclidean Distance Algorithm:**  
  - Provides quick computation of similarity between real-time inputs and stored baselines.
  
- **Other Models Considered:**  
  - SVM, KNN, and Logistic Regression were evaluated during initial experiments using Python’s scikit-learn.

### Technical Specifications

- **Hardware:**  
  - Minimum: Intel Core i5/Ryzen 5, 8–16 GB RAM, SSD storage.
  - GPU recommended for accelerated model training.

- **Software:**  
  - Programming Language: Python 3.8+  
  - Libraries: scikit-learn, TensorFlow/Keras (for potential deep learning), pandas, NumPy, OpenCV (for gesture analysis)  
  - Database: SQLite (development) / PostgreSQL (production)

- **Security Measures:**  
  - Encryption via AES for stored data and TLS for communication channels.
  - Role-based access control and anonymization to meet privacy regulations (GDPR/CCPA).

---

## Methodology and Implementation

### Data Collection & Preprocessing

- **Custom Desktop Application:**  
  - Developed to record keystroke metrics:
    - **Hold Time:** Duration between key press and release.
    - **Keydown-Keydown Time:** Interval between consecutive key presses.
    - **Keyup-Keydown Time:** Delay between key release and subsequent key press.
  - Data was collected from 15 users to create a diversified behavioral dataset.

- **Preprocessing:**  
  - Normalization and noise reduction applied to raw data for consistency.
  - Feature extraction performed to distill meaningful statistics for model training.

### Model Training and Evaluation

- **Training Process:**  
  - Supervised learning models were trained using scikit-learn.
  - Employed Train-Test Split and K-Fold Cross Validation to ensure model robustness.
  
- **Performance Metrics:**  
  - Achieved over **95% detection accuracy** with a low false positive rate.
  - Average response time measured under **500 ms**.

### Real-Time Monitoring and Response

- **Continuous Authentication:**  
  - System monitors user behavior continuously and compares it to stored baselines.
  - On detection of an anomaly, the alert system triggers re-authentication prompts or terminates the session.

- **Alert Mechanism:**  
  - Configurable thresholds allow customization of alert sensitivity.
  - Admin dashboard displays logs and system health metrics.

---

## Project Demonstration and Results

- **Live Demonstration:**  
  - Real-time interface displayed continuous data capture and anomaly detection.
  - Admin dashboard provided visual insights into user sessions and system alerts.
  
- **Results:**  
  - High detection accuracy and rapid response times validated system performance.
  - User feedback highlighted the unobtrusive design and improved security assurance.

- **Cost Analysis:**  
  - Using open-source tools and standard hardware made the solution cost-effective.

---

## Challenges and Learnings

### Technical Challenges Overcome

- **Dataset Unavailability:**  
  - Solved by building a dedicated data collection tool.
- **Real-Time Processing:**  
  - Achieved via efficient lightweight ML models and optimized data pipelines.
- **Behavior Variability:**  
  - Adaptive learning methods incorporated to handle behavioral fluctuations.
- **Data Security:**  
  - Implemented robust encryption and anonymization protocols.

### Performance Metrics Achieved

- **Detection Accuracy:** >95%
- **Response Latency:** Under 500 ms
- **Robust Cross-Validation Results:** Ensuring reliable model performance.

### User Feedback

- **Positive Aspects:**  
  - Seamless, unobtrusive monitoring.
  - Intuitive UI and minimal disruption to workflows.
- **Suggestions for Enhancement:**  
  - Integration of additional modalities like touchscreen data or voice recognition.

### Technical Limitations

- **Limited Modalities:**  
  - Only keystroke and mouse dynamics are used; other modalities could improve accuracy.
- **Cross-Device Variability:**  
  - Differences in hardware (keyboard layouts, mouse sensitivity) affect performance.
- **Small Dataset:**  
  - Only 15 users were included, limiting generalizability.

---

## Personal Technical Growth and Future Roadmap

### Key Learnings

- Gained proficiency in backend system design and data pipeline creation.
- Enhanced skills in building and optimizing machine learning models for real-time applications.
- Improved understanding of security protocols and privacy preservation in sensitive data environments.

### Planned Features and Future Improvements

- **Multi-Modal Support:**  
  - Include additional biometrics such as voice, facial recognition, or touch gestures.
- **Spoofing Detection:**  
  - Integrate adversarial learning techniques to detect mimicry attempts.
- **Expanded Dataset:**  
  - Recruit more users to improve model robustness and generalizability.
- **Enhanced User Customization:**  
  - Allow users to set their sensitivity preferences for anomaly detection.

### Scalability Considerations

- **Asynchronous Pipelines:**  
  - Adopt async I/O (using frameworks like Celery with Redis) to scale real-time processing.
- **Cloud Deployment:**  
  - Utilize Docker and Kubernetes for horizontal scaling.
- **Database Optimization:**  
  - Transition from SQLite to distributed databases such as PostgreSQL or NoSQL options for higher data volume.

### Model Improvements and Research Directions

- **Hyperparameter Tuning:**  
  - Use techniques like GridSearchCV or Bayesian optimization.
- **Incremental and Online Learning:**  
  - Implement models that update continuously with new behavioral data.
- **Explainable AI (XAI):**  
  - Incorporate tools (SHAP, LIME) to make model decisions more transparent.
- **Federated Learning:**  
  - Explore training on-device to boost privacy and reduce central data storage needs.

---

## Project Timeline

| Phase                  | Period          | Key Milestones                                      |
|------------------------|-----------------|-----------------------------------------------------|
| **Research & Planning**      | Apr 2024        | Literature review, problem definition, dataset planning |
| **Data Collection**    | May - Jun 2024  | Development of desktop app, collection from 15 users |
| **ML Model Development**      | Jun - Jul 2024  | Feature extraction, model training (Random Forest, SVM, KNN) |
| **System Integration**         | Aug 2024       | Integrating ML models with monitoring backend, encryption implementation |
| **Testing & Evaluation**       | Sep 2024       | Unit testing, integration testing, user acceptance testing (UAT) |
| **Final Deployment & Documentation** | Oct 2024      | System demo, report finalization, project submission |

---

## Installation and Usage

### Requirements

- **Python:** 3.8 or above  
- **Dependencies:**  
  - scikit-learn, pandas, numpy, TensorFlow/Keras, OpenCV, flask (for optional web dashboard)

### Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/behavioral-auth.git
   cd behavioral-auth
   pip install -r requirements.txt
   python app.py
   python model/train_model.py



