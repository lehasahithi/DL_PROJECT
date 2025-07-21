# 🛡️ ChildGuard: Missing Child Identification Using Deep Learning

ChildGuard is an AI-powered facial recognition system designed to assist in the identification and recovery of missing children. Built with deep learning and attention-enhanced convolutional networks, the system can reliably match child images—even with variations due to age progression, expressions, or accessories—making it suitable for real-world deployment in rescue operations.

---

## 🎯 Objective

To develop a robust, scalable, and intelligent system that:
- Identifies missing children accurately under real-world conditions.
- Handles variations such as pose, lighting, expression, and age.
- Generates synthetic training data to improve model generalization.
- Supports similarity matching for rapid identification.

---

## 🧠 Key Technologies Used

| Component            | Technology                                |
|---------------------|--------------------------------------------|
| Dataset             | UTKFace (Filtered for children aged 1–12)  |
| Preprocessing       | Image resizing, normalization, augmentation |
| Model Architecture  | Custom CNN + Attention Mechanisms          |
| Optimizer           | Adam                                        |
| Loss Function       | Binary Cross-Entropy                        |
| Similarity Matching | Cosine Similarity + Nearest Neighbor Search|
| Visualization       | OpenCV, Matplotlib                         |

---

## 🧩 Methodology

### 📁 1. Dataset
- **UTKFace Dataset** (20,000+ facial images)
- Filtered to retain **3,413** images of children aged 1–12.
- Images annotated with age, gender, and ethnicity.

### 🧼 2. Data Preprocessing
- Resized to `224x224`
- Pixel normalization [0, 1]
- Augmentations:
  - Horizontal flip
  - Rotation
  - Zooming
  - Brightness/contrast shift
  - Noise injection

### 🧠 3. Model Architecture
- **Custom CNN**
- Multiple Conv + MaxPooling layers
- **Attention Layers** to focus on critical facial features
- ~89 million trainable parameters
- Final output: feature embedding vectors

### 🏋️‍♂️ 4. Training
- Optimizer: Adam
- Loss: Binary Cross-Entropy
- Multiple epochs for feature embedding learning

### 📈 5. Similarity Matching
- Test image embedding is compared to dataset embeddings
- Cosine Similarity used for closeness calculation
- Nearest Neighbor Search returns top match

### 🖼️ 6. Visualization
- Side-by-side comparison of test and matched images
- Similarity score display
- Tools: OpenCV and Matplotlib

---

## 💡 Flow Diagram

```text
+-------------------+       +-------------------+       +---------------------+
| Dataset Collection| --->  | Data Preprocessing| --->  | CNN + Attention     |
+-------------------+       +-------------------+       | Feature Extractor   |
                                                        +----------+----------+
                                                                   |
                                                                   v
                                                +------------------+-------------------+
                                                | Similarity Matching (Cosine Distance)|
                                                +------------------+-------------------+
                                                                   |
                                                                   v
                                                +--------------------------------------+
                                                | Visualization of Test vs Matched Face|
                                                +--------------------------------------+

## ✅ Results
Distance Score: As low as 0.0085 (high similarity)

Robustness: Maintains accuracy under:

Motion blur

Occlusions (glasses, hair)

Age progression

Pose variations

Demonstrated real-world readiness for deployment

## 🔭 Future Scope
🕵️‍♂️ Real-time surveillance integration

📲 Mobile & cloud app deployment

📈 Age progression modeling

🛡️ Privacy-compliant face matching pipeline

📤 Automated alert systems for law enforcement

📚 Reference Dataset
UTKFace Dataset — A large-scale facial dataset with age, gender, and ethnicity labels

###👩‍💻 Authors
Bandaru Jaya Nandini

Mamidi Leha Sahithi

Siddareddy Gari Harshika

Suja Palaniswamy

### Institution:
Amrita Vishwa Vidyapeetham, Amrita School of Computing, Bengaluru
