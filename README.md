# NexiEmotionNet

Residual Convolutional Architecture with Dual Attention and Augmentation-Driven Training for Facial Emotion Recognition on RAF-DB.

**Paper:** NexiEmotionNet: Residual Convolutional Architecture with Dual Attention and Augmentation-Driven Training for Facial Emotion Recognition on RAF-DB  
**Authors:** Mohit Kadwal, Dr. Maya Ingle  
**Institution:** PIEMR Indore / DAVV Indore

---

## Requirements

Python 3.9+, PyTorch 2.0+, torchvision, scikit-learn, numpy, matplotlib

```bash
pip install torch torchvision scikit-learn numpy matplotlib
```

---

## Dataset

- RAF-DB: https://www.kaggle.com/datasets/shuvoalok/raf-db-dataset
- AffectNet: http://mohammadmahoor.com/affectnet/

Place dataset as:

```
dataset/DATASET/train/<emotion_class>/
dataset/DATASET/test/<emotion_class>/
```

---

## Training

Open `RAFDB_updated_Face_83.ipynb` in Google Colab and run all cells.

| Hyperparameter | Value |
|---|---|
| Epochs | 80 |
| Batch size | 32 |
| Optimizer | AdamW (lr=3e-4, wd=5e-4) |
| Loss | Class-Weighted Focal Loss (γ=1.5, ε=0.05) |
| Scheduler | Warmup Cosine (warmup=5, eta_min=1e-6) |
| Augmentation | RandAugment + CutMix + MixUp (epochs 5–70) |
| Evaluation | Five-Crop + 10x Multi-scale TTA |

---

## Results on RAF-DB

| Metric | Value |
|---|---|
| Overall Accuracy | 83.41% |
| Macro F1-Score | 77.27% |
| Parameters | 7.4M |
| FLOPs | 6.87G |
| Inference Time | 6.18ms |

---

## Pretrained Weights

Trained model weights (`emotion_model_v3.pt`) are available on Google Drive:  
[Download Pretrained Weights](https://drive.google.com/your-link-here)

*(Replace the link above with your actual Google Drive link after uploading)*

---

## Repository Structure

```
NexiEmotionNet/
├── RAFDB_updated_Face_83.ipynb    # Complete training and evaluation notebook
└── README.md                       # Project documentation
```

---

## Citation

```
Kadwal, M., Ingle, M., "NexiEmotionNet: Residual Convolutional Architecture
with Dual Attention and Augmentation-Driven Training for Facial Emotion
Recognition on RAF-DB", 2026.
```

---

## License

This project is intended for academic and research purposes only.
