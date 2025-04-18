# PROCTORAI - AI Powered Offline Proctoring System

## 🎯 Objective
PROCTORAI is a real-time, offline proctoring system designed to detect cheating behavior during paper-based examinations using cutting-edge deep learning models. The system eliminates the dependency on internet connectivity while improving reliability and accuracy over traditional manual invigilation.

---

## 🧠 Core Concept
Traditional exam monitoring is prone to human error, especially in large exam halls. While online proctoring exists, it cannot be applied in offline environments. PROCTORAI bridges this gap using AI-powered object and behavior detection to flag cheating attempts effectively, even without real-time human supervision.

---

## 🚀 Features
- Offline functionality: No internet needed during detection
- Multiple deep learning models evaluated and compared
- Attention-enhanced YOLOv8 for superior feature focus
- Real-time detection with frame-level precision
- Custom dataset of cheating and non-cheating scenarios
- Modular, scalable, and suitable for edge deployment

---

## 🏗️ Architecture

![Screenshot 2025-04-15 at 8 51 33 PM-picaai](https://github.com/user-attachments/assets/ff1f15de-4ff3-41bd-af91-dfae7a0d8e7a)

PROCTORAI evaluates and compares the following models:
- **LSTM+CNN**: For temporal anomaly detection in video
- **YOLOv8 (Baseline)**: Real-time object detection
- **YOLOv8 + ECA**: Efficient Channel Attention for enhanced feature sensitivity
- **YOLOv8 + Mixed Attention**: Uses CBAM, context-aware, and multi-scale attention
- **ViT (Vision Transformers)**: Captures global contextual information

### 🔍 ECA in YOLOv8
Efficient Channel Attention (ECA) highlights the most informative channels in feature maps without extra parameters. Integrated into YOLOv8’s C2f blocks, it significantly improves detection accuracy and reduces false positives.

---

## 🧪 Methodology
- **Dataset**:
  - 40 videos (20 cheating, 20 non-cheating) for LSTM+CNN
  - 3,522 manually annotated frames for YOLOv8, labeled via Roboflow
  - Data split: 70% training, 20% validation, 10% testing
- **Augmentation**:
  - Rotation, flipping, zoom, brightness adjustments, color jitter, perspective shifts
- **Training Tools**:
  - PyTorch and Ultralytics YOLOv8
  - ViT models trained with COCO JSON format
  - Attention modules integrated directly into YOLOv8 source

---

## 📊 Performance Highlights
| Model                 | Accuracy | Precision | Recall | mAP@50 | Speed (FPS) |
|----------------------|----------|-----------|--------|--------|--------------|
| YOLOv8 (baseline)    | 64%      | 0.62      | 0.60   | 0.64   | 250 FPS      |
| YOLOv8 + ECA         | **88%**  | 0.837     | 0.826  | 0.888  | **238 FPS**  |
| YOLOv8 + Mixed Attn  | 87.6%    | 0.84      | 0.81   | 0.876  | 225 FPS      |
| LSTM + CNN           | 96.67%   | 0.85     | 0.87   | N/A    | 9 FPS (P100) |
| Vision Transformer   | 81.4%    | 0.875     | 0.81   | N/A    | 15 FPS       |

---

## 📦 Output Examples
- Bounding boxes around suspicious behaviors
- Class labels like “cheating” or “non-cheating”
- Confusion matrix, precision-recall curves
- 
<img width="1440" alt="Screenshot 2025-04-18 at 1 05 03 PM" src="https://github.com/user-attachments/assets/8c45556d-f8ec-4924-9516-bf9e12ebe6aa" />
<img width="1438" alt="Screenshot 2025-04-18 at 1 05 18 PM" src="https://github.com/user-attachments/assets/51ba43f8-51aa-4a98-b0be-8a0767974c10" />
<img width="1440" alt="Screenshot 2025-04-18 at 1 05 34 PM" src="https://github.com/user-attachments/assets/7cdb7584-709d-4f25-b712-dd6361c1b169" />

---

## 📈 Real-World Deployment Readiness
- Inference tested on NVIDIA RTX 3090 (4.2 ms/image)
- Edge deployment planned using TensorRT on NVIDIA Jetson Nano
- Future support for audio input, keyboard monitoring, and XAI heatmaps

---

## 🔮 Future Scope
- Whisper detection via audio input
- Individualized tracking of suspicious behavior
- Integration with existing CCTV infrastructure
- Few-shot and continual learning
- Explainable AI with attention heatmaps
- Support for low-resource environments

---

## 👩‍💻 Team
- **Samridhi Raj Sinha** (70102100018)
- **Asmi Parikh** (70102100051)
- **Saakshi Jain** (70102100084)
- **Mentors**: Dr. Shubha Puthran & Dr. Supriya Agarwal

---

## 🙏 Acknowledgements
- Ultralytics for YOLOv8
- Authors of ECA and CBAM
- Roboflow for annotation tools

---

**Academic integrity starts with trust—and PROCTORAI makes it intelligent.**

