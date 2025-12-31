# Smart Attendance System - Phase 1

## Overview
A real-time face recognition attendance system using MTCNN for detection, FaceNet for embeddings, and SVM for classification with enhanced quality control.

## Architecture
- **Detection**: MTCNN (Multi-task Cascaded Convolutional Networks)
- **Embedding**: FaceNet (128-D face embeddings)
- **Classification**: SVM with StandardScaler
- **Quality Control**: Brightness & blur detection, multi-frame voting

## Features
✅ Real-time face detection at 30 FPS  
✅ Adaptive lighting detection  
✅ Blur detection (Laplacian variance)  
✅ Confidence thresholding (0.70)  
✅ Multi-frame voting (MIN_DETECTION_FRAMES=3)  
✅ Student registration with quality feedback  
✅ SVM model training with accuracy reporting  
✅ Detailed logging and statistics

## Installation

1. **Clone repository**
```bash
git clone https://github.com/jayavardhan143103/Smart-Attendance-System.git
cd Smart-Attendance-System
```

2. **Create virtual environment**
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Download FaceNet model**
- Download from: https://drive.google.com/file/d/1971Xk5RwedbudGgTIrGAL4F7Aifu7id1/view
- Create `models/` folder
- Place as: `models/facenet_keras.h5`

## Usage

```bash
python main.py
```

### Menu Options
1. **Test Camera** – Verify webcam & lighting
2. **Register New Student** – Capture images per student
3. **Train Model** – Train SVM on all students
4. **Test Recognition** – Real-time face recognition demo
5. **View Registered Students** – List all enrolled students
6. **Exit**

## Project Structure
```
smart_attendance/
├── config.py              # Configuration & constants
├── utils.py               # Helper functions
├── camera_manager.py      # Camera control
├── face_detector.py       # MTCNN detection
├── face_recognizer.py     # FaceNet + SVM
├── student_registration.py # Student enrollment
├── model_trainer.py       # SVM training
├── main.py                # CLI interface
├── requirements.txt       # Dependencies
└── README.md              # This file
```

## Configuration
Edit `config.py` to adjust:
- `CAMERA_INDEX` – 0 for laptop, 1 for external webcam
- `CONFIDENCE_THRESHOLD` – Default 0.70
- `MIN_DETECTION_FRAMES` – Multi-frame voting (default 3)
- `IMAGES_PER_STUDENT` – Default 30

## Phase 1 Status
✅ Completed:
- Core pipeline implemented
- Quality checks working
- Multi-frame voting logic
- Logging & statistics

## Next Phases
- Phase 2: Teacher authentication, hour-wise logic
- Phase 3: Database integration
- Phase 4: Web dashboard

## License
MIT

## Author
Jayavardhan (jayavardhan143103)
