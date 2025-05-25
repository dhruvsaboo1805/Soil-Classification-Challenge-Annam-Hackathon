
# Soil Type Classification using ResNet18

This project is part of the **Soil Image Classification Challenge** organized by Annam.ai at IIT Ropar. The goal is to classify soil images into one of four types: **Alluvial**, **Black**, **Clay**, or **Red**. The evaluation metric is the **minimum F1-score across all classes**.

## 📂 Dataset

- **Training Images**: 1222 labeled images
- **Test Images**: 341 unlabeled images
- **Labels File**: `train_labels.csv`
- **Test IDs File**: `test_ids.csv`
- **Image Format**: `.jpg`
- All images were resized to **224x224** using **Lanczos** resampling and converted to **RGB**.

## 🧠 Model

- **Architecture**: Pretrained **ResNet18**
- **Final Layer**: Modified to classify into 4 soil types
- **Framework**: PyTorch
- **Transforms**:
  - Resize (224x224)
  - RandomHorizontalFlip
  - Normalize using ImageNet statistics

## 📊 Training Strategy

- **Train/Validation Split**: 80/20 stratified by label
- **Loss Function**: CrossEntropyLoss
- **Optimizer**: Adam
- **Batch Size**: 32
- **Evaluation Metric**: Minimum F1-score across all classes

## 🛠️ Preprocessing

- All images were resized and saved to new directories (`train_resized`, `test_resized`)
- Label encoding was applied to convert soil types to numeric labels

## 🧪 Inference

- Test images are processed using the same transform pipeline
- Predictions are saved into a CSV file suitable for submission

## 📁 Folder Structure

```
├── train_labels.csv
├── test_ids.csv
├── train/
├── test/
├── train_resized/
├── test_resized/
```

## 🚀 How to Run

1. Resize images:
   ```python
   resize_images("train/", "train_resized", train_df["image_id"])
   resize_images("test/", "test_resized", test_df["image_id"])
   ```

2. Train the model:
   ```python
   # Run training loop (see notebook for details)
   ```

3. Generate predictions on test data and save submission file:
   ```python
   # Run inference and save predictions to CSV
   ```

## 📜 License

This code is intended for educational use as part of a Kaggle challenge.
