# 🏭 Raw Materials Classification

## 📖 Project Overview
This project implements a deep learning model for classifying raw materials (**wood, plastic, metal, glass**) based on image texture using **Convolutional Neural Networks (CNNs)** and **Transfer Learning**.  

- **Architectures:** ResNet18, EfficientNet-B1, MobileNetV3  
- **GUI:** Streamlit-based interface for image upload, predictions, confidence scores, and Grad-CAM visualizations  
- **Applications:** Industrial sorting and smart recycling systems

---

## ✨ Bonus Feature
**Texture Robustness under Varying Lighting, Shadow & Glare Conditions**  
> The model recognizes materials correctly even under different illumination, shadow, or glare conditions, simulating real factory settings.  

Achieved through **heavy augmentations** using Albumentations:  
`RandomBrightnessContrast`, `RandomShadow`, `GaussNoise`, `MotionBlur`

---

## 📂 Dataset

- **Main Dataset:** Kaggle – Material Dataset New (~15,000 images, focused on JPEGImages for classification)
-  **Link Dataset:** https://www.kaggle.com/datasets/alistairking/recyclable-and-household-waste-classification
- **Additional Custom Images:** Collected under extreme lighting, deep shadows, and strong glare (~15,000 images with augmentations)  
- **Total Images:** ~40,000  
- **Class Distribution:** Balanced across materials (visualized in `preprocessing/data_exploration.ipynb`)

---

## 🧠 Models Implemented
| Model           | Source        | Role                        |
|-----------------|---------------|----------------------------|
| **ResNet18**        | torchvision   | Baseline                   |
| **EfficientNet-B1** | timm          | Best accuracy              |
| **MobileNetV3**     | torchvision   | Lightweight & fast         |

**Training Details:** Pre-trained on ImageNet, fine-tuned with custom augmentations  
**Explainability:** Grad-CAM for model attention visualization  
**Bonus Features:** Heavy lighting augmentations, top-3 predictions with confidence scores

---

## 📊 Results
*(To be updated after final training)*

- **ResNet18:** xx% accuracy  
- **EfficientNet-B1:** xx% accuracy (Best performing)  
- **MobileNetV3:** xx% accuracy  

Confusion matrices, accuracy graphs, and performance under varying lighting are available in the `docs/` folder.

---

## 🖥 GUI Features
- Upload an image
- Display top-3 predicted classes with confidence scores
- Grad-CAM visualizations
- View accuracy/confusion matrix
- Compare results across models  

**Framework:** Streamlit

---

## ⚙️ Setup Instructions

```bash
# Clone repository
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
│   ├── custom_lighting_images/     # Custom images for robustness
│   └── README.md                   # Dataset description
├── models/                         # Trained .pth files
├── gui/                            # GuiApp.py
├── src/                            # DataLoader.py, Train.py, Model_defs.py
├── preprocessing/                  # Dataset preprocessing & augmentation
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
Name               GitHub Username        Main Responsibility
Doha Mohamed       Doha-Mohamed2005       "GUI Development, Grad-CAM, Repo Owner"
Zeinab Mahmoud     0xZeinab               "GUI Assistance & Grad-CAM Integration"
Ahmed Ashraf       ahmedashrafmedo        "Training, Testing, Evaluation"
Abanoub Shenouda   Abanoub Shenouda       "Training, Testing, Evaluation"
Farid Elsharkawi   FaridElsharkawi        "Data Collection & Heavy Augmentations"
---
🛠 Dataset Preprocessing
1️⃣ Data Upload & Exploration

Downloaded Kaggle dataset and extracted

Analyzed class distribution and visualized (e.g., bar plot)

Reviewed sample images for quality and balance

2️⃣ Image Preprocessing

Resize to 224x224

Normalize pixel values to [0,1]

Label extraction from filenames

3️⃣ Data Augmentation

Geometric: Random flips, rotations, crops

Color: Hue and saturation adjustments

Lighting Robustness (BONUS): Brightness/contrast, shadows, glare

4️⃣ Dataset Split

Train: 70%, Validation: 15%, Test: 15%

Stratified splitting to preserve class balance

5️⃣ Saved Configuration

preprocessing_config.json includes:

Image size

Class mapping

Batch size

Augmentation settings
---
⚡ Challenges & Learnings

Handling imbalanced lighting conditions required custom data collection and augmentations

Integrating Grad-CAM improved model interpretability

Collaborative GitHub usage ensured smooth teamwork
---
📝 Final Deliverables

Code repository (GitHub) with dataset links, models, and GUI code

Trained models and evaluation metrics

Functional GUI application (web-based via Streamlit)

Final report detailing dataset selection, model comparison, results, and challenges

Bonus demonstration of lighting robustness

