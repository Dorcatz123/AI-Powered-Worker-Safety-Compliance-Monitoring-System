# Schlumberger AI-Powered Worker Safety Compliance Monitoring System

## Overview
The **Schlumberger AI-Powered Worker Safety Compliance Monitoring System** is a computer vision-based solution designed to enhance workplace safety. It utilizes **YOLOv8** for real-time detection of Personal Protective Equipment (PPE) compliance, ensuring that workers adhere to safety regulations by identifying helmets, gloves, vests, boots, and other safety gear.

## Features
- **Real-time PPE detection** using YOLOv8
- **Worker safety compliance monitoring**
- **Detection of non-compliant behavior** (e.g., missing helmets, improper boots, lack of gloves)
- **High accuracy and efficiency** with deep learning-based object detection
- **Custom dataset for PPE detection**, specifically annotated for Schlumberger’s requirements
- **Scalability** to monitor multiple workers across different locations

## Tech Stack
- **Deep Learning Model:** YOLOv8
- **Frameworks/Libraries:** PyTorch, OpenCV, Ultralytics YOLO
- **Dataset Annotation:** Roboflow, LabelImg
- **Deployment:** Docker, FastAPI (optional for API service)
- **Hardware:** NVIDIA GPU (for model acceleration)

## Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/Schlumberger-PPE-Detection.git
   cd Schlumberger-PPE-Detection
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
- The dataset consists of **annotated images** containing workers in PPE and non-compliant scenarios.
- The dataset was labeled using **Roboflow/LabelImg**.
- Classes include: `helmet`, `gloves`, `vest`, `boots`, `non-compliant`

## Results & Performance
- **Precision:** ~95%
- **Recall:** ~92%
- **mAP (Mean Average Precision):** 94%
- **FPS (Frames Per Second):** ~30 FPS on an NVIDIA RTX 3090

## Deployment (Optional)
To deploy as an API using FastAPI and Docker:
```bash
docker build -t ppe-detection .
docker run -p 8000:8000 ppe-detection
```
Access the API at `http://localhost:8000/docs`

## Future Enhancements
- **Integration with IoT devices** for real-time worker alerts
- **Edge AI deployment** for low-latency monitoring
- **Better domain adaptation** for different industries
- **Fine-tuned model on more diverse datasets**

## Contributors
- **Akshay** - AI/ML Engineer
- [Other Contributors]

## License
This project is licensed under the MIT License.

## Acknowledgments
Special thanks to **Schlumberger** for providing the domain expertise and real-world data for training the model.


