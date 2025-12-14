# 🏭 Raw Materials Classification

## ✨ Bonus Feature
**Texture Robustness under Varying Lighting, Shadow & Glare Conditions**  
> Model recognizes materials correctly even under different illumination, shadow, or glare conditions, simulating real factory settings.

---

## 📂 Dataset (GitHub Requirements)
**Main Dataset:** Kaggle – Raw Material Images for Classification  
**Additional Custom Images:** Collected by team under extreme lighting, deep shadows, and strong glare (for bonus robustness)

## 🧠 Models Implemented (3 Architectures)
| Model           | Source        | Role                        |
|-----------------|---------------|----------------------------|
| **ResNet18**        | torchvision   | Baseline                   |
| **EfficientNet-B1** | timm          | Best accuracy              |
| **MobileNetV3**     | torchvision   | Lightweight & fast         |

**Bonus Features**
- Heavy augmentations using Albumentations (RandomBrightnessContrast, RandomShadow, GaussNoise, MotionBlur, etc.)
- Grad-CAM visualization in Streamlit GUI
- Top-3 predictions with confidence scores
- Robust performance under factory-like lighting conditions

## ⚙️ Setup Instructions
```bash
pip install -r requirements.txt
streamlit run gui/GuiApp.py

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
├── notebooks/                       # EDA & experiments
├── requirements.txt
└── README.md

##Team Members & Roles (6 members )
Name               GitHub Username        Main Responsibility
Doha Mohamed       Doha-Mohamed2005       "GUI Development, Grad-CAM, Repo Owner"
Zeinab Mahmoud     0xZeinab               "GUI Assistance & Grad-CAM Integration"
Ahmed Ashraf       ahmedashrafmedo        "Training, Testing, Evaluation"
Abanoub Shenouda   Abanoub Shenouda       "Training, Testing, Evaluation"
Farid Elsharkawi   FaridElsharkawi        "Data Collection & Heavy Augmentations"
Omar Ragab         Omarragab66            "Data Collection & Preprocessing"

🛠 Dataset Preprocessing
1️⃣ Data Upload & Exploration

Kaggle dataset downloaded and extracted.

Class distribution analyzed and visualized.

Sample images reviewed for quality and balance.

2️⃣ Image Preprocessing

Resize to 224x224.

Normalize pixel values to [0,1].

Label extraction from filenames.

3️⃣ Data Augmentation

Geometric: random flips, rotations, crops.

Color: hue and saturation adjustments.

🎯 Lighting Robustness (BONUS): brightness/contrast, shadows, glare for factory simulation.

4️⃣ Dataset Split

Train: 70%, Validation: 15%, Test: 15%.

Stratified splitting to preserve class balance.

5️⃣ Saved Configuration

preprocessing_config.json includes:

Image size

Class mapping

Batch size

Augmentation settings

settings

📊 Results (To be updated after final training)

ResNet18: xx%

EfficientNet-B1: xx% ← Best

MobileNetV3: xx%

Confusion matrix & accuracy graphs → docs/ folder
