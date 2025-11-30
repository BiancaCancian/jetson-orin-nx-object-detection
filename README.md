## **System Setup & Environment Used**

This project was developed and tested using the following environment:

### **Operating System**
- Ubuntu 22.04 (aarch64)  
- NVIDIA L4T 36.3  
- JetPack 6.0.0  

### **AI and Vision Frameworks**
- DeepStream 6.2  
- Python 3.10  
- PyTorch (Jetson build)  
- Torchvision (Jetson build)

### **Hardware**
- NVIDIA Jetson Orin NX  
- USB Webcam  

### **Container Runtime**
- Docker 29.0  

### **GPU / Compute Stack**
- CUDA 12.2  
- TensorRT 8.6  
- cuDNN 8.9  

---

For this specific inference example we use YOLOv8 (Ultralytics). Inference runs on the GPU using the compute stack versions listed above.

PyTorch and Torchvision on Jetson must match the JetPack version. Use Jetson-compatible wheels (generic PyTorch wheels will not work on aarch64).

## **Quick Start**

1. Create the environment:

sudo apt update
sudo apt install -y python3-pip python3-venv git libopencv-dev v4l-utils

python3 -m venv yoloenv
source yoloenv/bin/activate
pip install --upgrade pip

2. Install Ultralytics (YOLOv8):

pip install ultralytics

3. Install PyTorch compatible with your CUDA version  
Example for CUDA 12.1 (JetPack 6.x):

pip install torch==2.9.1 torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121

4. Download a YOLO model:

yolo download model=yolov8n.pt

5. Fix webcam window if it does not open:

pip uninstall -y opencv-python-headless
pip install opencv-python

6. Run inference:

yolo predict model=yolov8n.pt source=0 show=True

7. Verify GPU usage:

jtop










