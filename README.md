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
Benchmarking ML Model Inference: Evaluating the performance of inference code in both Python and C. (C wins!)
Real-time Anomaly Detection: Implementing on-device anomaly prediction for CNC milling operations using the Seeed nrf52840 Sense.
Hardware setup for Data Collection
The hardware setup includes a Seeed nRF52840, which facilitates the collection of vibration data. Equipped with a 6-axis IMU, the sensor efficiently captures real-time vibrations during CNC milling operations.

We integrated a sensing component into the XCarve CNC machine to collect vibration data during the efficient and precise milling of small squares on an acrylic sheet. The square patterns were initially designed in CAD, specifying their sizes and positions, and then imported into CAM software, which generated the G-Code instructions required to operate the CNC machine.

Milling operations were performed using a flat-end mill bit, with the spindle speed tested at various RPMs ranging from 3,000 to 12,000 to determine the optimal settings. XY Speed tested at 30, 40, and 50 mm/sec.

Training and Deploying ML Model
Process flow :

The data collected from the previous steps serves as the foundation for further analysis and the development of machine learning (ML) models. These models are designed to predict CNC milling failures and trigger alerts effectively. To achieve this, the process involves the following steps:

Data Preparation Collected X cut, Y cut, corners, circle, Danger (intentional anomolies to sim faults)
Feature extraction
Model training
Model optimization
Model conversion to run on Micro-controller
Load into arduino library
Upload to microcontroller

Lots of dep/perm issues getting arduino cli, edgeimpulse cli, codex, and microcontroller to talk nicely with each other. Patience required.


Resources & Docs:
https://github.com/Seeed-Studio/wiki-documents/blob/ccdf4ad4ed44606772a1a5ae96ee2a0514fc6897/sites/en/docs/Sensor/SeeedStudio_XIAO/SeeedStudio_XIAO_ESP32S3/Application/Edgeimpulse/EdgeImpulse.md
https://github.com/Seeed-Studio/wiki-documents/blob/ccdf4ad4ed44606772a1a5ae96ee2a0514fc6897/sites/en/docs/Sensor/SeeedStudio_XIAO/SeeedStudio_XIAO_nRF52840-Sense/Embedded_ML/XIAOEI.md
https://studio.edgeimpulse.com/studio/955053/impulse/1/deployment
https://docs.edgeimpulse.com/hardware/boards/seeed-xiao-nrf52840-sense
https://wiki.seeedstudio.com/XIAOEI/


Next Add capability for:
temperature 
current https://www.seeedstudio.com/XIAO-2-Channel-Wi-Fi-AC-Energy-Meter-Bundle-Kit.html
microphone https://colab.research.google.com/github/tensorflow/tflite-micro/blob/main/tensorflow/lite/micro/examples/micro_speech/train/train_micro_speech_model.ipynb
