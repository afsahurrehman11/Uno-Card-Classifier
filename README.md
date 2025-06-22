<h1 align="center">🎴 Uno Card Classifier 🎴</h1>

<p align="center">
  <a href="https://github.com/yourusername/yourrepo"><img src="https://img.shields.io/badge/GitHub-Repository-blue" alt="GitHub Repository"></a>
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-green" alt="License"></a>
</p>

---

### <span style="color: blue;">📸 Dataset</span>
The dataset consists of photographs of a physical Uno deck. For each card, four variants were captured:
- **Full card**: The entire card is visible on a **white background**.
- **Tilted angle**: The camera is positioned lower and tilted away from the top, captured on a **deep red color background** (often resembling maroon).
- **Corner only**: Only a corner of the card is shown, on a **white background**.
- **Half card**: Centered directly above with half the card visible, on a **white background**.

These images are stored in the `./Sample Dataset/Sample Orignal Images/` folder.

---

### <span style="color: green;">🔄 Data Augmentation</span>
To increase dataset size and variety, the following augmentations were applied to each image:
- **Original**: No changes applied.
- **Rotate 45°**: Rotates the image by 45 degrees.
- **Rotate 90°**: Rotates the image by 90 degrees.
- **Rotate -45°**: Rotates the image by -45 degrees.
- **Adjust Brightness (Darker)**: Reduces brightness by a factor of 0.7.
- **Adjust Brightness (Brighter)**: Increases brightness by a factor of 1.3.
- **Add Gaussian Noise (Stronger)**: Adds Gaussian noise with a standard deviation of 50.
- **Skew 15° Camera Angle**: Applies a 15-degree skew to simulate a camera angle change.
- **Affine Transform (Camera Angle 30°)**: Applies an affine transformation to simulate a 30-degree camera angle change.

Augmented images are stored in the `./Sample Dataset/After Augmenation/` folder.

---

### <span style="color: yellow;">🧠 Model Architecture</span>
The classifier is a custom **Artificial Neural Network (ANN)** built entirely from scratch in Python, without relying on frameworks like TensorFlow or PyTorch. It consists of:
- **Input Layer**: Matches the dataset's feature size.
- **Hidden Layer**: 64 neurons.
- **Output Layer**: 5 neurons (one per class: blue, green, pink, yellow, wild).

---

### <span style="color: red;">📊 Training and Results</span>
The model was trained for 250 epochs with a learning rate of 0.01. Evaluation on the test set produced the following results:

| Metric    | Value  |
|-----------|--------|
| Accuracy  | 97.99% |
| Precision | 0.98   |
| Recall    | 0.98   |
| F1 Score  | 0.98   |

---

### <span style="color: purple;">🖼️ Sample Images: Yellow Card Example</span>
This section showcases the original four variants of a yellow Uno card and examples of its augmented versions.

#### Original Variants
| Full Card (White BG) | Tilted Angle (Deep Red BG) | Corner Only (White BG) | Half Card (White BG) |
|----------------------|----------------------------|------------------------|----------------------|
| <img src="./Sample%20Dataset/Sample%20Orignal%20Images/49.jpg" > | <img src="./Sample%20Dataset/Sample%20Orignal%20Images/13.jpg" > | <img src="./Sample%20Dataset/Sample%20Orignal%20Images/50.jpg" > | <img src="./Sample%20Dataset/Sample%20Orignal%20Images/1.jpg" > |

#### Augmented Examples (From Full Card)
| Rotate 45° | Adjust Brightness (Darker) | Add Gaussian Noise |
|------------|----------------------------|--------------------|
| <img src="./Sample%20Dataset/After%20Augmenation/yellow_1_full_rotate45.jpg" width="200"> | <img src="./Sample%20Dataset/After%20Augmenation/yellow_1_full_brightness_dark.jpg" width="200"> | <img src="./Sample%20Dataset/After%20Augmenation/yellow_1_full_noise.jpg" width="200"> |

---

### <span style="color: black;">🛠️ Requirements</span>
- Python 3.x
- `numpy`
- `matplotlib`
- `scikit-learn`

Install with:
```
pip install numpy matplotlib scikit-learn
```

---

### <span style="color: orange;">🚀 How to Use</span>
1. Install the required libraries.
2. Load the pre-trained model:
```python
import pickle
with open('model.pkl', 'rb') as f:
    W1, b1, W2, b2 = pickle.load(f)
```
3. Use the `predict` function (defined in the code) to classify new Uno card images.

---

### <span style="color: gray;">📝 Notes</span>
- The dataset is not included due to its size, but sample images are provided in `./Sample Dataset/`.
- The ANN was implemented from scratch, showcasing a fully custom-built solution.
- The model is saved as `model.pkl` for easy loading.

---

*Enjoy this custom-built Uno Card Classifier!*
