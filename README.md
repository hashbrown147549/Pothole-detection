# 🕳️ Pothole Detection using YOLOv8 🚧

This project implements a deep learning-based approach to detect potholes in road images using [YOLOv8](https://github.com/ultralytics/ultralytics). The model was trained on a custom dataset and can be used to predict potholes in images or video streams.

---

## 📁 Project Structure
pothole-detection/
├── dataset/ # Unzipped training dataset
│ ├── train/
│ ├── valid/
│ └── data.yaml
├── runs/ # YOLOv8 training outputs
│ └── detect/
│ └── train/
├── screenshots/ # Input images for testing
├── best.pt # Trained YOLOv8 model weights
├── predict.py # Inference script
└── README.md # Project overview


## 🧠 Model Details

- **Model**: YOLOv8n (nano)
- **Framework**: Ultralytics YOLOv8
- **Training Epochs**: 50
- **Dataset Format**: YOLO (image-label pairs)
- **Input Image Size**: 640x640

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/hashbrown147549/pothole-detection.git
cd pothole-detection
```
### 2. Install Dependencies
bash
Copy code
```pip install ultralytics opencv-python```
### 3. Run Inference
python
Copy code
```from ultralytics import YOLO

model = YOLO("best.pt")
results = model.predict(
    source="screenshots/potholee.png",
    save=True,
    conf=0.25
)
```
Output image will be saved to runs/detect/predict/.

📊 Training Summary
Metric	Value
Precision	0.91
Recall	0.88
mAP@0.5	0.89
Epochs	50
Model Size	~4.7MB

📦 Dataset
Source: Roboflow custom dataset (link)

Format: YOLOv5 PyTorch export

Includes: Images of roads with/without potholes and annotations

🛠️ Future Work
Video stream pothole detection

Real-time integration with Raspberry Pi or Jetson Nano

Edge deployment using ONNX/TensorRT

 

