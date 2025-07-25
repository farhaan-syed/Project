# 🔍 Fooling YOLO: A Dive Into Adversarial Attacks on Object Detection

## 🎯 Objective
Can we trick a powerful AI model like YOLOv5, which detects cars in images, by adding tiny, invisible noise?

> Spoiler: Yes, we can.

This notebook explores **adversarial robustness**—testing whether minute, human-imperceptible changes can fool neural networks trained for object detection.

---

## 🧪 What You’ll Learn
- How YOLOv5 works for object detection  
- How to generate adversarial examples using **FGSM (Fast Gradient Sign Method)**  
- How to measure the robustness of pretrained vision models  
- How fragile AI systems can be against subtle attacks  

---

## 🛠️ Steps Covered

### 1. Setup & Dependencies
- Clone the [YOLOv5 repository](https://github.com/ultralytics/yolov5)
- Install `CleverHans`, PyTorch, and other required Python packages
- Load YOLO model utilities and attack functions

### 2. Get the Dataset
- Import a vehicle image dataset from Kaggle
- Use images of cars, trucks, and roads for testing

### 3. Load the YOLOv5 Model
- Use pretrained `YOLOv5s` for fast, lightweight detection
- Prepare model for inference on test images

### 4. Generate Adversarial Attacks
- Define a function to inject imperceptible noise into images
- Use **FGSM**, a single-step gradient-based attack method

### 5. Run the Attack
- Apply noise to a batch of 20 vehicle images
- Compare YOLOv5 predictions before and after attack

### 6. Evaluate Robustness
- Track detection performance post-attack
- Test across multiple `ε` values (perturbation strengths)
- Plot robustness decay as `ε` increases

---

## 📈 Results

- Even a tiny `ε = 0.02` can reduce YOLOv5's detection performance **to 0%**
- Visualizations show a steep collapse in object detection accuracy as attacks intensify
- **✅ Robust:** Same predictions on clean and attacked images  
- **❌ Fooled:** Predictions differ post-attack

---

## 🚨 Why This Matters

AI systems deployed in safety-critical settings—like:
- 🚗 Self-driving vehicles  
- 🧠 Medical imaging  
- 🛸 Military surveillance  

...must be resilient to adversarial manipulation. A sticker, a shadow, or slight distortion might obscure pedestrians or vehicles from detection.

This demo reveals the hidden fragility of vision models and emphasizes the need for **robustness testing in real-world AI deployments**.

---

## 🔗 References
- [YOLOv5](https://github.com/ultralytics/yolov5) by Ultralytics  
- [CleverHans Library](https://github.com/cleverhans-lab/cleverhans)  
- FGSM Paper: [Explaining and Harnessing Adversarial Examples (Goodfellow et al., 2015)](https://arxiv.org/abs/1412.6572)

---

## 📌 To Try This Yourself
- ⚡ Enable a GPU runtime (recommended: Google Colab)  
- 🔑 Upload your Kaggle API key to access datasets  
- ▶️ Run notebook cells in sequence to reproduce results  

---

## 🧠 Author's Note
This isn’t just a technical demo—it’s a wake-up call.  
If you can fool a vision model this easily...  
**what else can be fooled?**
