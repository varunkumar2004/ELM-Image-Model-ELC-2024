# ELM-Image-Model-ELC-2024

This repository contains the trained deep learning model and relevant assets used for real-time stress detection in facial expressions. It was developed as part of the **SafeSpace ELC 2024** project, an Android-based solution aimed at monitoring emotional well-being using on-device image processing and machine learning.

## 🧠 About the Model

The model is based on a Convolutional Neural Network (CNN) architecture trained to classify stress levels from facial expressions. It analyzes key emotional indicators such as tension, sadness, anger, and neutral states using image data captured in real-time.

* Input: Grayscale facial images
* Output: Probability scores for predefined emotional states (e.g., `stressed`, `neutral`, `calm`, `anxious`)
* Framework: TensorFlow / Keras
* Deployment Format: `.tflite` for Android integration

## 🚀 Use in Production

This model is deployed as part of the [SafeSpace-ELC-Android](https://github.com/varunkumar2004/SafeSpace-ELC-Android) mobile app, which captures real-time video feed from the front camera, processes facial images locally, and provides instant feedback on emotional stress levels.

## 📊 Dataset

* Source: Public emotion datasets (FER+, AffectNet)
* Classes: `neutral`, `stressed`, `happy`, `sad`, `angry`
* Preprocessing: Histogram equalization, face cropping using Haar cascades, normalization

> **Note**: Dataset not included in this repo due to licensing constraints. Please use publicly available emotion detection datasets for training.

## 🛠️ How to Train (Optional)

1. Clone the repository:

   ```bash
   git clone https://github.com/varunkumar2004/ELM-Image-Model-ELC-2024.git
   ```

2. Export to `.tflite`:

   ```python
   converter = tf.lite.TFLiteConverter.from_saved_model('path_to_model')
   tflite_model = converter.convert()
   ```

## 🤝 Integration with Android App

To integrate this model into Android (as done in SafeSpace):

* Place `stress_model.tflite` into the `assets` folder of your Android app.
* Use TensorFlow Lite Interpreter for inference on real-time camera frames.
* Refer to [SafeSpace-ELC-Android](https://github.com/varunkumar2004/SafeSpace-ELC-Android) for the full implementation.

## 🧾 License

This repository is intended for educational and research purposes. Please check respective datasets and libraries for their licenses.
