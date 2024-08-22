### **🚀 Vehicle Tracking Using YOLOv5 + DeepSORT**

Welcome to the Vehicle Tracking repository! This project combines the power of **YOLOv5** for object detection and **DeepSORT** for multi-object tracking to track vehicles in videos, identify their directions, and count them. Whether you are a researcher, traffic analyst, or AI enthusiast, this repository is your go-to resource for implementing an efficient vehicle tracking system.

---

### **📌 What is it?**

This repository provides a complete pipeline for detecting and tracking vehicles using YOLOv5 and DeepSORT. It is designed to track vehicles only within a specific Region of Interest (ROI) and categorize them based on their directions. 

### **🎯 Why do we do it?**

Accurate vehicle tracking is crucial for traffic management, urban planning, and safety analysis. This project enables high precision in monitoring traffic flow and vehicle behavior by using state-of-the-art models like YOLOv5 for detection and DeepSORT for tracking.

### **👥 Who is this for?**

This project is ideal for:
- **Traffic Management Authorities**: To monitor and analyze traffic patterns.
- **Researchers**: Studying vehicle movement and traffic behavior.
- **AI Enthusiasts**: Learning and experimenting with object detection and tracking models.
  
### **🛠️ How did we do it?**

#### **1. Detection with YOLOv5**
- **YOLOv5** is used for detecting vehicles. The model has been fine-tuned on the AIC-HCMC-2020 dataset to enhance detection accuracy.
  
#### **2. Tracking with DeepSORT**
- **DeepSORT** assigns each detected vehicle a unique ID, allowing for consistent tracking across frames.

#### **3. Cosine Similarity for Direction Assignment**
- Vehicle tracks are matched with predefined directions using cosine similarity, ensuring accurate direction classification.

#### **4. Counting Vehicles by Direction**
- Vehicles are counted based on their classified directions, providing an efficient way to monitor traffic flow.

### **📊 Results**

After running the full pipeline, a `.csv` file is generated containing detailed tracking information such as:
- **Track ID**: Unique identifier for each vehicle.
- **Frame ID**: Frame number of the video.
- **Bounding Box**: Coordinates of the detected vehicle.
- **Color**: Visualization color for each vehicle.
- **Direction**: Classified direction of the vehicle.
- **First/Last Point & Frame**: Initial and final positions and frames of the vehicle.

Example format:
```
track_id |	frame_id |	box	| color |	label |	direction |	fpoint |	lpoint |	fframe |	lframe
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
2	| 3	| [607, 487, 664, 582]	| (144, 238, 144) |	0	| 1	| (635.5, 534.5)	| (977.0, 281.5)	| 3	| 109
```

### **🔍 Dataset**
- **AIC-HCMC-2020 Dataset**: This dataset is used for model training and evaluation. 
- **ROI and Direction Annotations**: Provided in a JSON format, matching video names and defining the regions and directions for tracking.

### **🔧 Installation & Inference**

#### **1. Install Dependencies**
```bash
pip install -r requirements.txt
```

#### **2. Run the Pipeline**
```bash
python run.py --input_path=<input video or dir> --output_path=<output dir> --weight=<trained weight>
```

#### **Extra Parameters**:
- `--min_conf`: Minimum confidence for detection.
- `--min_iou`: Minimum IoU for detection.

If you need a guideline, follow this [kaggle_notebook](https://www.kaggle.com/code/quanhoangngoc/demo-counting/notebook)

### **🏅 Achievements**
- **High Precision and Recall**: The YOLOv5 models fine-tuned on the AIC-HCMC-2020 dataset demonstrate exceptional performance.
- **Versatile Application**: This project can be adapted for various traffic monitoring and management use cases.

### **🔗 References**
- [YOLOv5](https://github.com/ultralytics/yolov5)
- [DeepSORT](https://github.com/ZQPei/deep_sort_pytorch)

---
