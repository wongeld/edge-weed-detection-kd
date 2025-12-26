# Enhancing Farm Efficiency with Knowledge-Distilled Weed Detection

**Autonomous Weed and Crop Detection for Resource-Constrained Environments**

📄 Research-oriented implementation  
🌍 Focused on smallholder farming in Sub-Saharan Africa  
🧠 Knowledge Distillation • Computer Vision • Edge AI

---

## Overview
Weed infestation is a major threat to food security in Sub-Saharan Africa, causing crop yield losses of up to 100% in severe cases. Smallholder farmers—who make up the majority of producers—rely heavily on manual weeding, which is labor-intensive and hazardous. While chemical herbicides reduce labor, they introduce serious environmental and health risks.

This project investigates **knowledge distillation (KD)** as a practical approach to deploying **high-accuracy weed and crop detection models on resource-constrained edge devices**, enabling safer, more sustainable precision agriculture.

---

## Key Contributions
- Trained a high-capacity **YOLOv11n teacher model** for weed/crop detection
- Applied **response-based knowledge distillation with temperature scaling**
- Systematically evaluated distilled student models:
  - YOLOv5n
  - YOLOv5s
  - YOLOv8n
- Compared KD-based training against **standard supervised training**
- Analyzed trade-offs between **accuracy, speed, and model size** for edge deployment

---

## Methodology Summary
- **Task**: Binary object detection (Crop vs. Weed)
- **Datasets**: Maize-weed and precision agriculture datasets
- **Input Resolution**: 640 × 640
- **Teacher Model**: YOLOv11n
- **Students**: YOLOv5n, YOLOv5s, YOLOv8n
- **KD Approach**: Response-Based Knowledge Distillation with temperature scaling  
- **Evaluation Metrics**: mAP50, mAP50-95, precision, recall, inference time, throughput

---

## Results Highlights

| Model | Size (MB) | mAP50 | Speedup | Accuracy Retention |
|------|----------|-------|--------|-------------------|
| YOLOv5n (KD) | 3.8 | 0.819 | 2.7× | 97.4% |
| YOLOv5s (KD) | 13.6 | **0.845** | 0.8× | **100.4%** |
| YOLOv8n (KD) | 6.2 | 0.830 | 1.7× | 98.6% |
| YOLOv8n (Normal) | 6.2 | 0.836 | **5.4×** | 99.3% |

**Key Insight:**  
Knowledge distillation is highly effective for *ultra-lightweight models* (YOLOv5n), but **direct training can outperform KD** for modern architectures like YOLOv8n.

---

## Practical Implications
- **YOLOv5n (3.8 MB)** is suitable for deployment on low-cost devices (e.g., Raspberry Pi)
- Enables real-time weed detection for robotic spraying
- Reduces reliance on herbicides and manual labor
- Supports sustainable, AI-driven agriculture in resource-limited settings

---

## Limitations
- Limited crop and geographic diversity
- No real-world field deployment testing
- Evaluated on a single GPU platform (NVIDIA L4)
- Environmental factors (rain, dust, shadows) not tested

---

## Future Work
- Field trials on smallholder farms
- Deployment on edge devices (Raspberry Pi, Jetson Nano)
- INT8 / FP16 quantization
- Extension to other African crops
- Integration with robotic spraying systems

---

## Code
The full experimental pipeline is provided as a Jupyter Notebook:
- `notebooks/Weed_and_Crop_Detection_Model.ipynb`

The notebook includes:
- Data preprocessing
- Model training
- Knowledge distillation setup
- Evaluation and comparison

---

## Citation
If you use or reference this work, please cite:

> Wongel Daniel, *Enhancing Farm Efficiency: Autonomous Weed and Crop Detection using Knowledge Distillation*, 2025.

---

## Author
**Wongel Daniel**  
MSc Artificial Intelligence, Carnegie Mellon University Africa
