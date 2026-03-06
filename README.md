# Blood Cell Detection Using YOLO

## Problem Description

Complete Blood Count (CBC) testing is a common diagnostic procedure used in medical laboratories. Blood smear images are analyzed to identify and count different types of blood cells. Traditionally, this task is performed manually by laboratory technicians, which can be time-consuming and may introduce human error.

This project builds an automated system that detects and classifies blood cells using a YOLO object detection model. The system identifies three types of blood cells in microscope images:

- Red Blood Cells (RBC)
- White Blood Cells (WBC)
- Platelets

The goal is to evaluate whether automated detection can assist laboratory workflows and help process large numbers of samples efficiently.

---

## Dataset

The project uses the **Blood Cell Count and Detection (BCCD)** dataset.

- **Dataset:** BCCD (Blood Cell Count and Detection)
- **Source:** Roboflow Universe
- **Classes:** RBC, WBC, Platelet
- **Images:** ~360 blood smear images
- **Annotations:** Bounding boxes

The dataset contains microscope images of blood samples where each cell is labeled with a bounding box indicating its location and class.

---

## Dataset Download

The dataset was downloaded directly from **Roboflow** using the following code:

```python
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="EFLPqZqkSgfffwDkag7v")
project = rf.workspace("joseph-nelson").project("bccd")
version = project.version(3)
dataset = version.download("yolo26")

```

### Install Required Libraries

Install all required dependencies using the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

## Steps to Run the Project

1. Download the dataset using the Roboflow script shown above.
2. Train the YOLO model using the downloaded dataset.
3. Run the trained model to detect blood cells in microscope images.

---

## Results

### Overall Model Performance

The improved **YOLO26s** model achieved the best performance.

| Metric | Value |
|------|------|
| mAP@50 | ~0.91 |
| mAP@50-95 | 0.652 |
| Precision | ~0.85 |
| Recall | ~0.91 |

These results indicate that the model successfully detects most blood cells within the validation dataset.
## Team Member Contributions

### Tanishq Rawat
- Dataset preparation and preprocessing  
- Model training and experimentation  
- Evaluation and analysis of model results  
- Project documentation  

### Vibhor Malik
- Background research and problem analysis  
- Experiment design  
- Results interpretation  
- Report preparation

## References

1. [Roboflow Universe — BCCD Dataset](https://universe.roboflow.com)  
2. [Ultralytics YOLO Documentation](https://docs.ultralytics.com)

