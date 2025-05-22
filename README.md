# Drone & Bird Detection (RGB/IR Data)

This repository contains data exploration, preprocessing, detection and visualization notebook. This focuses on detecting and distinguishing between drones and birds using RGB and IR image pairs.


---

## Dataset Overview Summary

### Folder Structure
```
Dataset/
├── RGB/
│   ├── images/      # RGB image files
│   └── labels/      # YOLO-format labels for RGB
└── IR/
    ├── images/      # IR (infrared) image files
    └── labels/      # YOLO-format labels for IR
```

### Image Format
- All images are in `.jpg` format

### Label Format (YOLOv5)
```
<class_id> <x_center> <y_center> <width> <height>
```
- All coordinates are normalized to [0, 1]

### Color Channels
- RGB: 3-channel
- IR: 1-channel grayscale

### Image Shape
- Fixed resolution: (256, 320)
- Aspect Ratio: 1.25 (width / height)

### Data Type
- 8-bit unsigned integers (`uint8`)

### File Counts
- IR Images: 57,580  
- RGB Images: 57,580  
- IR Labels: 57,580  
- RGB Labels: 57,580

### Sample Filenames
| Index | IR Filename | RGB Filename |
|-------|-------------|--------------|
| 0 | IR_BIRD_00160_001_png.rf.69a4850f48f928d.jpg | BIRD_00160_001_png.rf.83d82e1339a851b2e3f37bc0631284d8.jpg |
| 1 | IR_BIRD_00160_001_png.rf.d4c132ef2f33b3e.jpg | BIRD_00160_001_png.rf.f9423fe5f9ef7f4f3419addc319192f4.jpg |
| 2 | IR_BIRD_00160_002_png.rf.b2a71ef76532c70.jpg | BIRD_00160_002_png.rf.665902ae9388b9016e15cee3a6c03905.jpg |
| 3 | IR_BIRD_00160_002_png.rf.cac0484d8f6c2f8.jpg | BIRD_00160_002_png.rf.69513ceff2d17a600fb32df906c30eb0.jpg |

Note: The `.rf.<hash>.jpg` suffix denotes unique samples (possibly augmented or hashed).

---

## Project Structure
```bash
├── data_exploration.ipynb        # Jupyter notebook
├── README.md                     # Project readme (this file)
├── requirements.txt              # Python dependencies
├── runs/                         # Output predictions
└── SceneVideos/                  # Sample scene prediction videos
```

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/Drone-Bird-Detection-RGB-IR-Data.git
cd Drone-Bird-Detection-RGB-IR-Data
```

### 2. Create Environment
```bash
python -m venv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook
```bash
jupyter notebook
```

---

## Results

The following are sample prediction outputs and scene reconstructions generated from the YOLO model:

https://github.com/MrAlbaraa/Drone-Bird-Detection-RGB-IR-Data/tree/main/SceneVideos 

If videos aren't uploaded, you can view them in the `SceneVideos/` directory or run the inference code provided in the notebook.

---

## Requirements

See `requirements.txt`:
```text
opencv-python
numpy
matplotlib
pandas
ultralytics
jupyter
```

---
