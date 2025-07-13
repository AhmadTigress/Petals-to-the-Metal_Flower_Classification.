## Key Metrics
- **Training Accuracy (sparse_categorical_accuracy)**: `12.88%`

- **Validation Accuracy**: `23.51%`

- **Training Loss**: `1.8324`

- **Validation Loss**: `2.0649`

-------

## Interpretation
1. **Low Accuracy (Underfitting)**

  - Both training (12.88%) and validation (23.51%) accuracies are very low, indicating the model is not learning effectively.

  - The validation accuracy is slightly higher than training, which is unusual and suggests potential issues like:

    - Data leakage (e.g., validation set contains easier samples).

    - Incorrect preprocessing (e.g., labels mismatched with images).

2. **Loss Values**

  - Training loss (1.83) is lower than validation loss (2.06), which is normal, but both are high—typical for a model making random guesses (baseline for 5 classes: ~20% accuracy).

3. Possible Causes

  - Frozen Base Model: ResNet50 layers are frozen (base_model.trainable = False), but the custom top layers may be too shallow (only 8 neurons) to adapt.

  - Learning Rate Issues: Exponential decay starts at 1e-5 (very small), slowing learning.

  - Data Problems: Check if:

    - Labels are correctly mapped (e.g., CLASS_NAMES matches dataset folders).

    - Images are properly decoded (e.g., decode_image normalizes to [0, 1] but ResNet50 expects preprocess_input).
