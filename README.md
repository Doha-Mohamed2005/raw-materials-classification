# 🏭 Raw Materials Classification

---

## 📖 Project Overview
This project implements a deep learning model for classifying raw materials (**wood, plastic, metal, glass**) based on **image texture** using **CNNs** and **Transfer Learning**.  

- **Architectures:** ResNet18, EfficientNet-B1, MobileNetV3  
- **GUI:** Streamlit-based interface for image upload, predictions, confidence scores, and Grad-CAM visualizations  
- **Applications:** Industrial sorting & smart recycling systems  

---

## ✨ Bonus Feature
**Texture Robustness under Varying Lighting, Shadow & Glare Conditions**  
> The model correctly recognizes materials even under varying illumination, shadows, or glare, simulating real factory settings.  

**Implemented via:**  
- Heavy augmentations using Albumentations:  
  `RandomBrightnessContrast`, `RandomShadow`, `GaussNoise`, `MotionBlur`

---

## 📂 Dataset

- **Main Dataset:** Kaggle – Material Dataset New (~15,000 images, focused on JPEGImages for classification)
- **Link Dataset:** https://www.kaggle.com/datasets/alistairking/recyclable-and-household-waste-classification
- **Custom Images:** ~15,000 additional images collected under extreme lighting and glare  
- **Total Images:** ~40,000  
- **Class Distribution:** Balanced across materials (see `preprocessing/data_exploration.ipynb`)

---

## 🧠 Models Implemented
| Model           | Source        | Role                        |
|-----------------|---------------|----------------------------|
| **ResNet18**        | torchvision   | Baseline                   |
| **Inceotion** | timm          | Best accuracy              |
| **Efficient_Net**     | torchvision   | Lightweight & fast         |

**Training Details:** Pre-trained on ImageNet, fine-tuned with custom augmentations  
**Explainability:** Grad-CAM for model attention visualization  
**Bonus Features:** Top-3 predictions + confidence scores, lighting robustness

---

## 📊 Results


- **ResNet18:** 88% accuracy  
- **Inceotion:** 96% accuracy (Best performing)  
-

Confusion matrices, accuracy graphs, and lighting robustness evaluation are available in `docs/`.

---

## 🖥 GUI Features
- Upload an image for prediction  
- Display **Top-3 predicted classes** with confidence scores  
- **Grad-CAM heatmap** visualization  
- View model comparison, accuracy, and confusion matrices  

**Framework:** Streamlit

---

## ⚙️ Setup Instructions
```bash
# Clone the repository
git clone https://github.com/Doha-Mohamed2005/raw-materials-classification.git
cd raw-materials-classification
# Install dependencies
pip install -r requirements.txt
# Run GUI
streamlit run gui/GuiApp.py
---
🗂 Repository Structure
raw-materials-classification/
├── data/
│   ├── custom_lighting_images/     # Custom images
│   └── README.md                   # Dataset description
├── models/                         # Trained .pth files
├── gui/                            # GuiApp.py
├── src/                            # DataLoader.py, Train.py, Model_defs.py
├── preprocessing/                  # Preprocessing & augmentation
│   ├── upload_dataset.ipynb
│   ├── data_exploration.ipynb
│   ├── preprocessing_pipeline.ipynb
│   ├── augmentations.py
│   ├── dataset_pipeline.py
│   └── preprocessing_config.json
├── docs/                           # Reports, confusion matrix, accuracy graphs
├── notebooks/                      # EDA & experiments
├── requirements.txt
└── README.md
---
👥 Team Members & Roles
Name	           GitHub Username	      Main Responsibility
Doha Mohamed	   Doha-Mohamed2005	    GUI Development, Grad-CAM, Repo Owner
Zeinab Mahmoud	   0xZeinab	          GUI Assistance & Grad-CAM Integration
Ahmed Ashraf	    ahmedashrafmedo	    Training, Testing, Evaluation
Abanoub Shenouda	Abanoub Shenouda	  Training, Testing, Evaluation
Farid Elsharkawi	FaridElsharkawi  	  Data Collection & Heavy Augmentations
Omar Ragab	       Omarragab66	      Data Collection & Preprocessing

All members contributed commits for collaboration.
---
🛠 Dataset Preprocessing

1️⃣ Data Upload & Exploration
Kaggle dataset downloaded & extracted
Analyzed class distribution and visualized
Sample images reviewed for quality & balance
---
2️⃣ Image Preprocessing
Resize to 224x224
Normalize pixel values [0,1]
Extract labels from filenames
---
3️⃣ Data Augmentation
Geometric: flips, rotations, crops
Color: hue & saturation adjustments
Lighting Robustness (BONUS): brightness/contrast, shadows, glare
---
4️⃣ Dataset Split
Train: 70% | Validation: 15% | Test: 15%
Stratified splitting to maintain class balance
---
5️⃣ Saved Configuration
preprocessing_config.json includes:
Image size
Class mapping
Batch size
Augmentation settings
---
📝 Final Deliverables
Complete GitHub repo with dataset links, models, and GUI code
Trained models & evaluation metrics
Functional Streamlit GUI
Final report with dataset, model comparison, results, and challenges
Bonus demonstration: lighting robustness
---
 
