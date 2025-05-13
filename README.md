
# Brain Tumor Classification Using ResNet-50 on MRI Images 
Introduction to Artificial Intelligence course Final project, HIT
Submitted by Maya Kimhi

>  **Achieved 98% classification accuracy on brain tumor MRI images using transfer learning with ResNet-50.**

---

Brain tumors are abnormal growths of cells in the brain or spinal cord. They pose a diagnostic challenge due to the blood-brain barrier. If misdiagnosed or untreated, they may cause severe brain damage or death.

MRI and CT scans are primary diagnostic tools, but interpretation requires highly trained radiologists. In Israel, a shortage of radiologists often leads to:
- Long wait times
- Diagnostic errors (10–20%)
This project aims to support early and accurate detection through AI.

---
##  Project Goals

- Classify MRI images into 4 categories:
  1. Glioma Tumor
  2. Meningioma Tumor
  3. Pituitary Tumor
  4. No Tumor

- Reduce incorrect diagnoses
- Shorten time to diagnosis
  
---
##  Dataset

- **Source**: [Kaggle Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset/data)
- **Size**: 7,023 labeled MRI images
- **Split**: 78% training, 22% testing
- **Classes**: 4 tumor types (as above)
- **Image Size**: Images resized to 224x224 to fit ResNet-50
  
---

##  Model Architecture

- Pretrained ResNet-50 model (on ImageNet)
- Custom classification head added:
  - Flatten
  - Dense Layer(s)
  - Dropout (optional)
  - Softmax Output Layer (4 classes)

---
## Workflow Summary

1. **Data Loading & Preprocessing**
   - RGB conversion, resizing, normalization
2. **Data Augmentation**
   - Rotation, shifting, zooming, flipping
3. **Model Compilation**
   - Loss: `categorical_crossentropy`
   - Optimizer: Adam
   - Metrics: Accuracy
4. **Model Training**
   - With and without augmentation
5. **Fine-tuning**
   - Unfreezing top layers of ResNet50 for additional training
6. **Evaluation**
   - Accuracy & loss on test data
   - Visualization of learning curves and predictions
---

##  Results
- Model trained with augmentation outperformed the non-augmented version
- Fine-tuning further improved classification accuracy
- Demonstrated strong generalization to test data

| Model Version        | Accuracy on Test Data |
|----------------------|-----------------------|
| Without Augmentation | ~92%                  |
| With Augmentation    | ~96%                  |
| Fine-Tuned Model     |    98%               |

---

##  Conclusion

- The final model achieved 98% accuracy on unseen test data, demonstrating strong generalization.
- This highlights the effectiveness of transfer learning with ResNet-50, especially when combined with:
  - Proper data preprocessing
  - Augmentation
  - Fine-tuning
    
---

### Future Enhancements:
- Test on additional datasets (external validation)
- Improve explainability (e.g., Grad-CAM visualizations)
- Integrate into a clinical workflow




