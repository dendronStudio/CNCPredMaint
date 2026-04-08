# CNCPredMaint
CNC mill Pred Maint, Optimization, Power conservation. AI/ML eeed nRF52840 + Edge Impulse
https://www.hackster.io/tiny-prism-labs/edgeai-for-predictive-maintenance-in-tormach-cnc-30e9e0#team

Edge ML-based predictive maintenance enables data processing directly on edge devices, such as battery-powered embedded systems installed on machines. By analyzing parameters like vibration, temperature, and usage frequency, Edge ML can predict failures and detect anomalies without relying on cloud connectivity.

This AI-driven approach offers several advantages over traditional cloud-based solutions, including:

Reduce latency
Lower bandwidth consumption
Enhanced data privacy,
Reliable performance
Works on low-connectivity environments.
Additionally, it significantly reduces resource consumption by leveraging real-time data analysis to:

Accelerate decision-making
Optimize maintenance schedules
Minimize unnecessary repairs
Reduce downtime
Project execution consists of two key phases:
Benchmarking ML Model Inference: Evaluating the performance of inference code in both Python and C.
Real-time Anomaly Detection: Implementing on-device anomaly prediction for CNC milling operations using the XIAO BLE Sense.
Hardware setup for Data Collection
The hardware setup includes a 3.7V 250mAh battery-powered Seeed Studio XIAO BLE Sense, which facilitates the collection of vibration data. Equipped with a 6-axis IMU, the XIAO BLE Sense efficiently captures real-time vibrations during CNC milling operations.

We integrated a sensing component into the Tormach XS Tech CNC machine to collect vibration data during the efficient and precise milling of small squares on an acrylic sheet. The square patterns were initially designed in CAD, specifying their sizes and positions, and then imported into CAM software, which generated the G-Code instructions required to operate the CNC machine.

Milling operations were performed using a flat-end mill bit, with the spindle speed tested at various RPMs ranging from 4, 000 to 12, 000 to determine the optimal settings.

Training and Deploying ML Model
Process flow :

The data collected from the previous steps serves as the foundation for further analysis and the development of machine learning (ML) models. These models are designed to predict CNC milling failures and trigger alerts effectively. To achieve this, the process involves the following steps:

Data Preparation
Feature extraction
Model training
Model optimization
Model conversion to run on Micro-controller
