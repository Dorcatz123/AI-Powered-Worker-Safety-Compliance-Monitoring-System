# AI-Powered Worker Safety Compliance Monitoring System

## Overview
The **AI-Powered Worker Safety Compliance Monitoring System** is a computer vision-based solution designed to enhance workplace safety. It utilizes **YOLOv8** for real-time detection of Personal Protective Equipment (PPE) compliance, ensuring that workers adhere to safety regulations by identifying helmets, gloves, vests, boots, and other safety gear.

![detect](https://github.com/Dorcatz123/AI-Powered-Worker-Safety-Compliance-Monitoring-System/blob/main/worker_github.jpg)

## Features
- **Real-time PPE detection** using YOLOv8
- **Worker safety compliance monitoring**
- **Detection of non-compliant behavior** (e.g., missing helmets, improper boots, lack of gloves)
- **Proprietery dataset for PPE detection**, specifically annotated for industry requirement.
- **Scalability** to monitor multiple workers across different locations

## Tech Stack
- **Deep Learning Model:** YOLOv8
- **Frameworks/Libraries:** Ultralytics YOLO
- **Dataset Annotation:** Roboflow
- **Hardware:** NVIDIA GPU (for model acceleration)

## Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/AI-Powered-Worker-Safety-Compliance-Monitoring-System.git
   cd AI-Powered-Worker-Safety-Compliance-Monitoring-System

   ```
2. **Create a virtual environment:**
   ```bash
   python -m venv env
   source env/bin/activate  # For Linux/Mac
   env\Scripts\activate  # For Windows
   ```
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Download YOLOv8 model weights:**
   ```bash
   wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8x.pt -O weights/yolov8x.pt
   ```

## Usage
### 1. Training
To train the model with your dataset:
```bash
python train.py --data data.yaml --epochs 50 --weights yolov8x.pt
```

### 2. Inference
To run inference on images or videos:
```bash
python detect.py --weights weights/yolov8x.pt --source test_images/
```

### 3. Live Detection (Using Webcam)
```bash
python detect.py --weights weights/yolov8x.pt --source 0
```

## Dataset
- The proprietery dataset was labeled using **Roboflow**.
- Classes include: `helmet`, `boots`, `coverall`, `no boots`, `no coverall`, 'no helmet'.
- The Classes an be extended to other classes.


## Future Enhancements
- **Integration with IoT devices** for real-time worker alerts
- **Edge AI deployment** for low-latency monitoring
- **Better domain adaptation** for different industries
- **Fine-tuned model on more diverse datasets and classes**

## Results:

![result](https://github.com/Dorcatz123/AI-Powered-Worker-Safety-Compliance-Monitoring-System/blob/main/test_result.png)


## Contributors
- **Akshay** - AI/ML Engineer
- **Anoop Sankar** -Data collection and project stakeholder

## License
This project is licensed under the MIT License.

## Acknowledgments
Special thanks to **Curvelogics pvt ltd and Schlumberger** for providing the domain expertise.


