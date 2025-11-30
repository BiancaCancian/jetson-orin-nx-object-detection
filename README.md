## **System Setup & Environment Used**

This project was developed and tested using the following environment:

### **Operating System**
- Ubuntu 22.04 (aarch64)  
- NVIDIA L4T 36.3  
- JetPack 6.0

### **AI and Vision Frameworks**
- DeepStream 6.2  
- Python 3.10  

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

For this specific inference example, we use YOLOv8 with the Ultralytics library which performed very well over 70 object classes. The inference runs on GPU with the stack versions listed above.

#### **Quick start**  

1. Create a virtual environment:  
   ```bash
   python3.10 -m venv venv
   source venv/bin/activate
