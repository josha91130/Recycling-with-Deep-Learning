# Recycling with Deep Learning: A CNN-Based Approach to Waste Classification

📄 **[Read the full article on Medium](https://medium.com/@schlin590/recycling-with-deep-learning-a-cnn-based-approach-to-waste-classification-034f36d47e87)**  
📍 Boston University – Questrom School of Business  
📘 BA865 – Advanced Analytics  
👥 Contributors: Ching Hsuan Lin, Zhe Yu Lin, Kayla Candice Huang, Pin Hao Pan

---

## What is Happening?

Waste management is a pressing global challenge, with landfills consuming vast land areas and contributing significantly to greenhouse gas emissions. In the United States alone, landfills occupy approximately **1.8 million acres**, and according to the **EPA**, municipal solid waste (MSW) landfills rank as the **third-largest source** of human-related methane emissions.

Despite a national recycling goal of **50% by 2030**, only **32.1%** of waste is currently recycled or composted, largely due to **higher recycling costs** compared to landfill disposal.

This project addresses the challenge by developing a **CNN-based image classification model** to categorize waste into:
- Plastic  
- General waste  
- Glass  
- Organic waste  
- Metal  
- Paper  

By integrating the model into **smart waste bins**, we aim to:
- Improve sorting accuracy  
- Reduce recycling costs  
- Support sustainability goals

---

## Why Tackle Waste Classification?

The environmental and economic impacts of inefficient waste management are significant. Our **fine-tuned CNN model** seeks to:
- **Assist governments** in achieving policy goals  
- **Support waste companies** in reducing costs  
- **Help communities** build better sorting habits

The ultimate goal is to **automate classification**, **reduce emissions**, and **promote a circular economy**.

---

## Dataset Creation and Preprocessing

### Data Collection  
- Custom dataset with real-world waste images  
- Labeled into 6 categories  
- Split into **training**, **validation**, and **test sets**

### Preprocessing Steps  
- Standardized image sizes  
- Ensured consistency for CNN input  
- Augmented images for robustness

---

## Neural Network Architectures

### Manually-Designed CNN Models  
Initial experiments with a custom-built lightweight CNN:
- **Augmentation**: Flips, rotations (±10%), zoom (±20%)  
- **Architecture**: 3-layer Conv2D (32→64→128), max-pooling, Flatten → Dense → Softmax  
- **Optimizers**: RMSprop and Adam  
- **Enhancements**: Dropout (30%), BatchNorm, GlobalAveragePooling, L2 regularization

### Model Evaluation  
- Best standalone model reached **70.8% accuracy**  
- Deeper models or excessive regularization led to **performance drop**  
- Motivated shift to **transfer learning**

---

## Pretrained Models with Transfer Learning

### ResNet50  
- Pretrained backbone  
- Custom dense head  
- **Drawbacks**: Too heavy, overfitting, peaked at **~28% accuracy**

### MobileNetV2  
- Lightweight and efficient  
- Two variants tested:  
  - **Standard fine-tuned**  
  - **CutMix-augmented** version  
- **Result**: CutMix-enhanced MobileNetV2 showed **highest validation accuracy**

---

## 🏁 Conclusion

Despite limited data, our **MobileNetV2-based CNN** achieved **83% accuracy**, proving the value of lightweight deep learning for:
- Faster, more accurate waste sorting  
- Cost reduction in recycling processes  
- Reduced environmental impact and landfill waste

This work shows how even modest AI systems can **modernize waste management** and promote **sustainability**.

---

## ⚠️ Challenges

Key issues faced:
1. Image format inconsistencies (JPEG, PNG, HEIC)
2. Multi-object images clashed with single-label design
3. Dataset too small for transformer-scale architectures

---

## 💡 Suggestions and Future Work

- **Multi-object recognition**: Enable multi-label detection for mixed-waste scenes  
- **Real-time edge inference**: Deploy quantized models on edge devices like Raspberry Pi  
- **Expanded data collection**: Improve generalization with diverse, larger datasets  
- **Vision transformers**: Try ViT and DeiT for higher accuracy  
- **Model ensembling**: Combine top models (MobileNetV2 + CutMix, EfficientNet, etc.) for improved performance
