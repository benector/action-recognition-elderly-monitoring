[🇧🇷 Português](index.md) | [🇺🇸 English](./)

# Application of Video-based Action Recognition Models to Elderly Monitoring

This project investigates the use of **Computer Vision models** for non-invasive monitoring of elderly individuals, focusing on the identification of **Activities of Daily Living (ADLs)** and risk situations without the need for wearable sensors.

## 🎯 Objectives

The main objective was to apply and evaluate an action recognition model that relies exclusively on **video input** to identify daily activities accurately and efficiently.

- **Action Identification:** Detect relevant events and atypical behaviors.
- **Autonomy Preservation:** Propose a non-intrusive solution that does not require body-worn devices.
- **Computational Efficiency:** Evaluate performance in terms of accuracy and computational cost.

## 📊 Dataset

The [**Toyota Smarthome Trimmed (TST)**](https://project.inria.fr/toyotasmarthome/) dataset was used.

**Characteristics:**  
It consists of videos of elderly individuals performing activities in real domestic environments.

**Granularity:**  
The dataset originally contains **31 action classes** with high postural variability.

**Protocol:**  
The **Cross-Subject protocol** was followed to evaluate the model’s ability to generalize across different individuals.

## 🛠️ Methods

The methodology is based on the **PoseConv3D framework**, which focuses on human pose representation.

**Pose Estimation:**  
Extraction of human keypoints (joints) from images to generate **2D heatmaps over time**.

**3D CNN Architecture:**  
The **X3D network** processes these heatmaps to capture spatial and temporal patterns of actions.

**Semantic Grouping:**  
Reduction of the original **31 action classes to 19 categories**. Similar actions that differed only by the manipulated object (e.g., drinking from a cup vs. drinking from a bottle) were merged to improve the learning of fundamental motion patterns.

## 📈 Results

The model demonstrated superior performance compared to the **original pose-based baseline method developed for the TST dataset** in terms of **mean class accuracy**.

### Full Dataset (31 classes)

- **Overall Accuracy:** 72.2%
- **Mean Class Accuracy:** 54.5%

### Grouped Dataset (19 classes)

- **Overall Accuracy:** 77.7%
- **Mean Class Accuracy:** 67.9%

**Efficiency:**  
Training the full dataset took approximately **12 hours on a single GPU**, making it more efficient than approaches that combine multiple input modalities (such as **RGB + Pose**).

## 🚀 Future Work

1. **Real-Time Monitoring:** Development of an infrastructure capable of sending immediate alerts in case of falls or risky behaviors.
2. **Posture-Based Grouping:** Explore grouping strategies based on body pose similarity (e.g., actions performed while sitting vs. standing) to reduce model confusion.
3. **Privacy and Edge Computing:** Implement the system on low-cost devices for local processing, ensuring that video data does not leave the elderly person’s residence.

## 💻 Technologies

- PyTorch
- [PySKL](https://github.com/kennymckormick/pyskl)
- MMCV
- HRNet
- OpenCV
- Python
- CUDA (GPU)

## 🔬 Techniques and Research Areas

- Human Action Recognition
- Computer Vision
- Deep Learning
- 3D Convolutional Neural Networks
- Human Pose Estimation (Heatmaps)

## 📄 Author

**Beatriz Aparecida Benedicto Heleno**  
MSc Student in Computer Science — Federal University of Juiz de Fora (UFJF)  
Research areas: Computer Vision and Computer Graphics

📄 Undergraduate Thesis:  
[Application of Video-based Action Recognition Models to Elderly Monitoring](http://monografias.ice.ufjf.br/tcc-web/tcc?id=1077)

🎥 **Project presentation (SEMIC 2025):**  
[Watch the presentation video](https://www.youtube.com/watch?v=alc41NiFxrg)

🔗 LinkedIn:  
[https://linkedin.com/in/beatrizbenedicto](https://linkedin.com/in/beatrizbenedicto)
