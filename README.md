🛡️ Botnet Detection from Network Traffic
A Machine Learning & Deep Learning Hybrid Approach

📌 Project Overview

Botnets are among the most serious cybersecurity threats, enabling large-scale attacks such as DDoS, data exfiltration, and unauthorized system control. Traditional signature-based detection systems struggle to identify evolving or zero-day botnet behaviors.

This project proposes an intelligent, data-driven botnet detection system using NetFlow-based network traffic features. We evaluate multiple models ranging from traditional machine learning to advanced deep learning architectures, culminating in a Hybrid DNN–LSTM model that captures both static feature interactions and temporal behavior patterns.

The project was developed as part of IS 734: Data Analytics for Cybersecurity at the University of Maryland, Baltimore County (UMBC).

👥 Team Members

Aryan Jagani

Aakash Nimgaonkar

Mansi Somnath Navale

Prathyusha Harish Kumar

Department of Information Systems, UMBC

🎯 Objectives

Detect botnet-generated traffic using flow-level (NetFlow) features

Compare traditional ML and deep learning approaches

Analyze the trade-offs between static and sequential modeling

Evaluate whether a hybrid architecture improves robustness and adaptability

📂 Dataset Description

Total Records: 5,472 network flows

Features: 19 NetFlow-based attributes

Target Variable:

0 → Normal traffic

1 → Botnet traffic

Feature Categories

Traffic statistics: Duration, payload byte size (PBS), total byte size (TBS)

Packet metrics: Packets sent, packets received

Rate-based features: Payload Byte Rate (PBR), Total Byte Rate (TBR)

Ratio features: Sender-to-Receiver Packet Ratio (SRPR)

🧹 Data Preprocessing

The following preprocessing steps were applied:

Removed non-informative identifiers (IP addresses, port numbers)

Handled missing values

Normalized numerical features using StandardScaler

Split data into 80% training / 20% testing

Reshaped data into sequences for LSTM-based models

📊 Exploratory Data Analysis (EDA)

EDA revealed clear behavioral differences between normal and botnet traffic:

Botnet flows show higher payload byte rates

Packet ratio features (e.g., SRPR) strongly indicate anomalous behavior

Correlation analysis guided feature importance and model selection

Visualizations included:

Feature importance plots

Correlation matrices

Distribution plots for key flow features

🧠 Models Implemented
1️⃣ Random Forest (Baseline)

Strong performance on structured tabular data

Used 5-fold stratified cross-validation

Primary evaluation metric: F1-score

2️⃣ Deep Neural Network (DNN)

Fully connected dense layers with ReLU activation

Captures non-linear feature interactions

Sigmoid output layer for binary classification

3️⃣ Long Short-Term Memory (LSTM)

Designed to capture temporal and sequential patterns

Models coordinated botnet behaviors over time

Useful for detecting command-and-control activity

4️⃣ Hybrid DNN–LSTM (Proposed Model)

Parallel architecture combining:

DNN branch → static feature learning

LSTM branch → temporal dependency modeling

Outputs concatenated and passed to a final classification layer

Uses EarlyStopping to reduce overfitting

🧪 Experimental Results
Model	Best Accuracy
Random Forest	89%
DNN	83.84%
LSTM	83.38%
Hybrid DNN–LSTM	83.29%
Key Insights

Random Forest performs best on static datasets

DNN achieves the highest accuracy among deep learning models

LSTM improves recall by modeling temporal behavior

Hybrid model offers better adaptability for real-world, evolving traffic

⚠️ Challenges

Limited dataset size (risk of overfitting)

Difficulty forming meaningful sequences from tabular NetFlow data

Overfitting in deep and hybrid models at higher epochs

Similarity between low-activity botnet traffic and normal flows

Complex hyperparameter tuning

✅ Conclusion

This project demonstrates that machine learning and deep learning models are effective for botnet detection, with all evaluated approaches achieving over 80% accuracy. While Random Forest excels on static datasets, the Hybrid DNN–LSTM model provides greater robustness and adaptability by combining feature-level and temporal learning.

The hybrid approach is better suited for real-world network environments, where attack patterns continuously evolve.

🚀 Future Work

Expand dataset size and diversity

Explore attention mechanisms and Transformer-based models

Implement real-time detection using streaming NetFlow data

Extend binary classification to multi-class botnet family detection

Integrate explainable AI (XAI) for better interpretability

🛠️ Technologies Used

Python

Pandas, NumPy

Scikit-learn

TensorFlow / Keras

Matplotlib, Seaborn

📄 Files in This Repository

botnetdetection from network traffic.ipynb – Model implementation and experiments

BOTNET DETECTION FROM NETWORK TRAFFIC.docx – Detailed project report

BOTNET POSTER.pdf – Conference-style project poster

📚 References

Key references are listed in the full report, including works published in IEEE Access, ACM, and leading cybersecurity journals
