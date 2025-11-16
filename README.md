# Waste Classification Using MobileNetV2

An AI-based system that classifies waste into predefined categories using a deep learning model and a Tkinter-based GUI for real-time prediction.

---

## 1. Project Objective

The objective of this project is to automate waste segregation using a deep learning model (MobileNetV2) trained on an image dataset.  
The system classifies waste into six categories:

- Cardboard  
- Glass  
- Metal  
- Paper  
- Plastic  
- Trash  

A Tkinter GUI allows users to upload an image and receive instant predictions.

---

## 2. Dataset Details

**Dataset Used:** Kaggle Waste Classification Dataset  
**Total Classes:** 6 (cardboard, glass, metal, paper, plastic, trash)  
**Total Images:** Approximately 2500–3000  
**Image Size:** Resized to 224 × 224 pixels  

**Data Split:**
- Training: 80%  
- Testing: 20%  

**Preprocessing:**
- Pixel rescaling (1/255)
- Data augmentation:
  - Rotation  
  - Zoom  
  - Width/height shift  
  - Horizontal flip  

---

## 3. Algorithm / Model Used

**Model:** MobileNetV2 (Transfer Learning)

MobileNetV2 is a lightweight convolutional neural network suitable for real-time and mobile-friendly applications.

**Steps Followed:**

1. Loaded MobileNetV2 with pretrained ImageNet weights  
2. Froze base layers for feature extraction  
3. Added custom layers:
   - GlobalAveragePooling  
   - Dense(128, ReLU)  
   - Dropout(0.3)  
   - Dense(6, Softmax)  
4. Trained for 10 epochs (frozen)  
5. Unfroze selective layers and fine-tuned with a low learning rate  

**Training Details:**
- Loss Function: Categorical Crossentropy  
- Optimizer: Adam  
- Metrics: Accuracy, Precision, Recall, F1-score  

---

## 4. Results

### Model Performance

| Metric               | Score          |
|----------------------|----------------|
| Training Accuracy    | 85–90%         |
| Validation Accuracy  | ~80%           |

### Graphs Generated
- Training vs. Validation Accuracy  
- Training vs. Validation Loss  

### Confusion Matrix Analysis
- High accuracy for paper, plastic, cardboard  
- Lower accuracy for trash due to class imbalance  

### GUI Performance
The Tkinter application performs real-time predictions with high responsiveness.

---

## 5. Conclusion

This project successfully developed an AI-powered waste classification system using MobileNetV2.  
The model achieves strong performance with approximately 80% validation accuracy and integrates effectively into a Tkinter GUI for practical, real-time prediction.

The system demonstrates:
- High classification accuracy  
- Lightweight and deployable model architecture  
- Real-world applicability for smart recycling systems  

---

## 6. Future Scope

Possible improvements include:

- Expanding and balancing the dataset  
- Deploying the model on IoT or mobile platforms  
- Integrating a real-time camera stream  
- Developing a web interface instead of a desktop GUI  
- Adding more waste categories  

---

## 7. References

1. Sandler, M., et al. "MobileNetV2: Inverted Residuals and Linear Bottlenecks." CVPR, 2018.  
2. Kaggle Waste Classification Dataset – https://kaggle.com  
3. TensorFlow Documentation – https://www.tensorflow.org  
4. Keras API Reference – https://keras.io  
5. Tkinter Documentation – https://docs.python.org/3/library/tkinter.html
