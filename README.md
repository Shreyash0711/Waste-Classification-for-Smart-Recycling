# Waste Classification for Smart Recycling ♻️

A deep learning project using TensorFlow and MobileNetV2 to classify images of trash into six categories: **plastic**, **metal**, **glass**, **paper**, **cardboard**, and **trash**.

## 📂 Dataset

- Based on [TrashNet dataset](https://github.com/garythung/trashnet)
- 6 classes: `plastic`, `metal`, `glass`, `paper`, `cardboard`, `trash`
- Images resized to `224x224`
- Train/validation split: 80/20

## 🧠 Model

- Pretrained base: `MobileNetV2` (`imagenet` weights, frozen)
- Custom head:
  - `GlobalAveragePooling2D`
  - `Dense(128, relu)`
  - `Dropout(0.2)`
  - `Dense(6, softmax)`

### ⚙️ Training Setup

- Epochs: `10`
- Optimizer: `Adam`
- Loss: `categorical_crossentropy`
- Image augmentation: `rescale`, `rotation`, `zoom`, etc.
- EarlyStopping + ReduceLROnPlateau used as callbacks

## 📊 Performance

| Metric         | Value     |
|----------------|-----------|
| Final Train Accuracy     | 91.5%    |
| Final Validation Accuracy | 81.4%    |
| Final Validation Loss     | 0.56     |
| Best Epoch | 10/10 |
| Inference Speed | ~27s/epoch (64 steps) |

