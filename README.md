# 🚗 Low-Light Vehicle & License Plate Detection using YOLOv8

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![YOLOv8](https://img.shields.io/badge/Model-YOLOv8-red)
![OpenCV](https://img.shields.io/badge/OpenCV-Image_Processing-green)

**An advanced object detection project designed to identify vehicles and license plates in challenging low-light conditions.**

This project addresses the limitations of standard detection models in dark environments by implementing a robust **Image Preprocessing Pipeline**. By leveraging **CLAHE** and **Gamma Correction**, the system enhances image visibility and contrast before feeding data into the **YOLOv8** model, significantly improving detection accuracy at night.

---


---

## 💡(Methodology)

เพื่อให้โมเดลทำงานได้ดีในที่มืด ผมได้สร้าง Preprocessing Pipeline เพื่อปรับปรุงภาพดังนี้:

Color Space Conversion: The RGB image is converted to the LAB Color Space to isolate the Luminance (L) channel from color information.

CLAHE (Contrast Limited Adaptive Histogram Equalization): Applied strictly to the L-channel. This enhances local contrast in dark regions without amplifying noise, which is crucial for night-time images.

Gamma Correction: Adjusts the overall brightness (luminance) while preventing overexposure in already bright areas (e.g., car headlights or street lamps).

YOLOv8 Detection: The enhanced image is processed by a custom-trained YOLOv8 model to detect vehicles and license plates.

📂 Project Structure
---

## 📂 โครงสร้างโปรเจค (Project Structure)

Repository นี้ประกอบด้วย 3 ส่วนหลัก ดังนี้:

| ไฟล์ | รายละเอียด |
| :--- | :--- |
| **`01_Data_Prep_and_Training.ipynb`** | **Part 1:** การเตรียมข้อมูล (Data Preprocessing), การประยุกต์ใช้ CLAHE/Gamma กับ Dataset และการเทรนโมเดล YOLOv8 |
| **`02_Model_Evaluation.ipynb`** | **Part 2:** การวัดผลและวิเคราะห์ เปรียบเทียบผลลัพธ์ระหว่างภาพต้นฉบับ (Original) กับภาพที่ปรับแสงแล้ว (Enhanced) |
| **`03_Video_Inference.ipynb`** | **Part 3:** การนำโมเดลไปทดสอบกับไฟล์วิดีโอจริง (Video Inference Pipeline) |

---

## 📊 การวิเคราะห์ผลลัพธ์ (Performance Analysis)

จากการเปรียบเทียบระหว่างโมเดลปกติ (Baseline) และโมเดลที่ใช้เทคนิค Image Enhancement:

### 1. การเปรียบเทียบเชิงคุณภาพ (Visual Comparison)
โมเดลที่ผ่านการปรับปรุงภาพ (Enhanced) สามารถตรวจจับวัตถุในมุมมืด หรือวัตถุที่กลืนไปกับพื้นหลังได้ดีกว่าอย่างเห็นได้ชัด


### 2. ประสิทธิภาพ (Metrics)
* **Model Architecture:** YOLOv8n (Nano)
* **Epochs:** 25
* **Result:** โมเดลสามารถรักษาสมดุลระหว่าง Precision และ Recall ได้ดี แม้จะมีการปรับแต่งภาพซึ่งอาจทำให้เกิด Noise เล็กน้อย แต่แลกมาด้วยการมองเห็นวัตถุที่ชัดเจนขึ้นมาก

---

## 🛠 (Tech Stack)

* **Language:** Python
* **Deep Learning:** Ultralytics YOLOv8
* **Computer Vision:** OpenCV (cv2), NumPy, Matplotlib
* **Environment:** Google Colab (GPU)
* **Dataset Management:** Roboflow

---

## 🚀(How to Run)

1.  Clone repository 
2.  openfile Notebook (`.ipynb`) in **Google Colab**
3.  install Libraries ที่จำเป็น:
    ```python
    !pip install ultralytics roboflow opencv-python-headless
    ```


---
