# Retail Shelf Detection System - FYP Project

**AI-powered system to detect product availability on retail shelves using YOLOv8**

---

## 🎯 Project Overview

This project aims to help FMCG (Fast-Moving Consumer Goods) companies monitor product availability on retail shelves in real-time. The system uses computer vision to detect whether products are present or missing from the first row of shelves, enabling:

- Automated out-of-stock detection
- Shelf compliance monitoring
- Inventory visibility for brands
- Reduced manual shelf audits

---

## 👥 Team

| Name | Role | Responsibilities |
|------|------|-----------------|
| Hassan | ML Lead & AI Engineer | YOLOv8 training, model optimization, system architecture |
| Moiz | Data Engineer | Image collection, data labeling, quality assurance |
| Rafay | Research Lead | Literature review, documentation, testing scenarios |

**Institution:** Habib University  
**Course:** Final Year Project (FYP)  
**Timeline:** Week 1 - November 2025

---

## 🔬 Technical Approach

### Model Architecture
- **Base Model:** YOLOv8n (nano) - optimized for speed
- **Training Strategy:** Transfer learning from COCO pre-trained weights
- **Fine-tuning:** Custom dataset of 6-8 retail SKUs

### Technology Stack
- **Deep Learning:** YOLOv8 (Ultralytics)
- **Data Labeling:** Roboflow
- **Training Environment:** Python 3.x, PyTorch
- **Data Augmentation:** Roboflow built-in augmentation
- **Version Control:** Git/GitHub

### Dataset
- **Initial Size:** 100-200 images (Week 1 proof-of-concept)
- **Target Size:** 500-1000 images (final deployment)
- **Classes:** 6 retail SKUs (Dayfresh flavors)
- **Scenarios:** All present, 1 missing, 2 missing, extreme cases

---

## 📊 Project Phases

### Phase 1: Proof of Concept (Week 1-2) ✅ *In Progress*
- [x] Environment setup (YOLOv8, dependencies)
- [x] Project structure created
- [x] Roboflow account setup
- [ ] Collect 100 training images
- [ ] Label dataset in Roboflow
- [ ] Train baseline model
- [ ] Validate detection accuracy

### Phase 2: Model Optimization (Week 3-4)
- [ ] Collect additional training data (200-500 images)
- [ ] Experiment with YOLOv8s/m models
- [ ] Hyperparameter tuning
- [ ] Achieve >85% mAP on validation set

### Phase 3: Real-world Testing (Week 5-6)
- [ ] Integration with Multinet camera
- [ ] Real-time inference pipeline
- [ ] Test in actual retail environment
- [ ] Performance benchmarking

### Phase 4: Deployment & Documentation (Week 7-8)
- [ ] Final model optimization
- [ ] Documentation & presentation
- [ ] Demo video creation
- [ ] Final report submission

---

## 🗂️ Project Structure
```
fyp_project/
├── data/
│   ├── raw_images/          # Original photos from phone/camera
│   ├── labeled_data/        # Roboflow exported dataset
│   └── test_images/         # Test scenarios (unseen data)
│       ├── all_present/
│       ├── one_missing/
│       └── two_missing/
├── models/
│   └── shelf_detection_v1/  # Trained model weights
├── notebooks/               # Jupyter notebooks for experiments
├── results/                 # Inference results, metrics, visualizations
├── documentation/
│   ├── labeling_guide.md
│   ├── literature_review.md
│   └── weekly_progress.md
├── train.py                 # Training script
├── test.py                  # Testing/inference script
├── requirements.txt         # Python dependencies
├── README.md               # This file
└── CHANGELOG.md            # Version history
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip package manager
- 4GB+ RAM (8GB recommended)
- GPU optional (speeds up training)

### Installation
```bash
# Clone repository
git clone <repo-url>
cd fyp_project

# Create virtual environment (optional but recommended)
python -m venv fyp_env
fyp_env\Scripts\activate  # Windows
# source fyp_env/bin/activate  # Linux/Mac

# Install dependencies
pip install -r requirements.txt

# Download YOLOv8 pretrained weights
python -c "from ultralytics import YOLO; YOLO('yolov8n.pt')"
```

### Training
```bash
# Train model (requires data.yaml in root)
python train.py

# Monitor training with TensorBoard (optional)
tensorboard --logdir models/shelf_detection_v1
```

### Testing
```bash
# Run inference on test images
python test.py

# Results saved to results/predictions/
```

---

## 📦 Dependencies
```txt
ultralytics>=8.0.0      # YOLOv8
opencv-python>=4.8.0    # Image processing
roboflow>=1.1.0         # Dataset management
matplotlib>=3.7.0       # Visualization
pandas>=2.0.0           # Data analysis
numpy>=1.24.0           # Numerical operations
pillow>=10.0.0          # Image handling
torch>=2.0.0            # PyTorch (auto-installed with ultralytics)
```

---

## 📈 Current Progress

### Week 1 Status (November 2025)

**Completed:**
- ✅ YOLOv8 environment setup (Hassan)
- ✅ Roboflow project created with 6 class labels
- ✅ Training & testing scripts written
- ✅ Project structure established
- ✅ Google Drive collaboration setup
- ✅ GitHub repository initialized
- ✅ Team roles assigned

**In Progress:**
- 🔄 Image collection (Moiz) - 100 images target
- 🔄 Literature review (Rafay) - 10-15 papers
- 🔄 Data labeling workflow setup

**Next Steps:**
- Label 100 images in Roboflow
- Train baseline YOLOv8n model
- Evaluate on test scenarios
- Document initial results

---

## 🎓 Research References

### Key Papers
1. Transfer Learning for Object Detection (to be added - Rafay)
2. YOLO for Retail Applications (to be added - Rafay)
3. Small Dataset Augmentation Strategies (to be added - Rafay)

See `documentation/literature_review.md` for comprehensive review.

---

## 🧪 Testing Scenarios

### Scenario A: All Products Present
- **Expected:** Detect all 6 SKUs
- **Metric:** 100% recall on present items

### Scenario B: 1-2 Products Missing
- **Expected:** Detect only present SKUs, ignore missing
- **Metric:** 0% false positives on missing items

### Scenario C: Extreme Cases
- **Expected:** Handle 2-3 products only, messy arrangements
- **Metric:** >70% mAP overall

---

## 📊 Success Metrics

| Metric | Week 1 Target | Final Target |
|--------|---------------|--------------|
| mAP@0.5 | 70-80% | 90-95% |
| Precision | 75%+ | 92%+ |
| Recall | 75%+ | 90%+ |
| Inference Speed | 30+ FPS | 30+ FPS |
| Training Time | <2 hours | <6 hours |

---

## 🤝 Contributing

### For Team Members

**Before making changes:**
```bash
git pull origin main
```

**After making changes:**
```bash
git add .
git commit -m "Descriptive message of what you changed"
git push origin main
```

**Branching workflow:**
- `main` - stable, working code only
- `dev` - active development
- `feature/your-name` - individual work

---

## 📝 Documentation

- **Labeling Guide:** `documentation/labeling_guide.md`
- **Literature Review:** `documentation/literature_review.md`
- **Weekly Progress:** `documentation/weekly_progress.md`
- **Changelog:** `CHANGELOG.md`

---

## 🐛 Known Issues

- None yet (Week 1)

Report issues in group chat or create GitHub issue.

---

## 📞 Contact

**Hassan (ML Lead)**
- Email: [your-email]
- GitHub: [your-github]

**Project Repository:** [repo-url]

---

## 📄 License

This is an academic project for Habib University FYP.  
All rights reserved to the project team.

---

## 🙏 Acknowledgments

- **Chronicler Labs** - AI engineering experience
- **Habib University** - Academic support
- **Multinet** - Camera hardware partner
- **Ultralytics** - YOLOv8 framework
- **Roboflow** - Data labeling platform

---

**Last Updated:** November 16, 2025  
**Version:** 0.1.0 (Week 1 - Proof of Concept)
