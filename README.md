# 🧠 TensorFlow Image Classification

This project is a simple **multi-class image classification** model built with **TensorFlow/Keras**. It classifies images into three categories:

- 🐶 **Dog**
- 🐯 **Tiger**
- 🍦 **Ice Cream**

The model uses RGB images fetched directly from public URLs and demonstrates how to build, train, and test a custom image classifier from scratch.

---

## 🔍 Overview

- ✅ Collects image data via URL (no dataset downloads required)
- 🖼️ Resizes and normalizes images to a consistent format (160x120, RGB)
- 🧠 Builds a dense neural network model (MLP)
- 🔄 Trains for 100 epochs with one-hot encoded labels
- 📊 Predicts new unseen images and prints class probabilities

---

## 🧰 Technologies Used

| Library        | Purpose                               |
|----------------|----------------------------------------|
| `TensorFlow`   | Neural network and training logic      |
| `Pillow (PIL)` | Image loading and processing           |
| `NumPy`        | Numerical arrays                       |
| `Requests`     | Downloading images from the internet   |
| `Matplotlib`   | (Optional) For plotting if needed      |

---

## 📁 Project Structure

```text
tensorflow-image-classification/
├── model_training.py        # Main script with model and data
└── README.md                # Project documentation
````

---

## 📦 Installation

To install the necessary dependencies:

```bash
pip install tensorflow numpy pillow requests
```

---

## 🚀 How It Works

1. **Loads images** from URL and resizes them to 160x120
2. **Normalizes** pixel values (0–1)
3. **Creates labeled dataset**:

   * Dogs → `[1, 0, 0]`
   * Tigers → `[0, 1, 0]`
   * Ice Cream → `[0, 0, 1]`
4. **Defines model**:

   * `Flatten` → `Dense(64)` → `Dense(32)` → `Dense(3, softmax)`
5. **Trains model** using categorical crossentropy
6. **Tests with a new image** and prints prediction result

---

## 🧪 Example Output

```text
Predicted Label: tiger
Raw Prediction: [0.01, 0.98, 0.01]
```

---

## 🖼️ Adding More Classes

Want to classify more categories? Just:

1. Add new image URLs.
2. Update the label vector `[0, 0, 0, 1, ...]`.
3. Adjust the output layer of the model to match the number of classes.

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

## 👤 Author

Created by [Peterson Chiquetto](https://github.com/petersonchiquetto)

---

## 💡 Future Ideas

* Switch to a **Convolutional Neural Network (CNN)** for better accuracy
* Add **image augmentation**
* Integrate with **Streamlit** or **Gradio** for a web-based interface
* Save and reload the model using `model.save()` and `tf.keras.models.load_model()`
