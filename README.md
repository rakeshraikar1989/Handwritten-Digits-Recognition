# Handwritten Digits Recognition

**Project ID:** PRCP-1002  
**Dataset:** MNIST handwritten digits  
**Task:** Multi-class image classification (digits 0–9)

## Project Overview

This project explores handwritten digit recognition using the MNIST dataset. Five classification models are implemented and compared:

1. K-Nearest Neighbors (KNN)
2. Logistic Regression
3. Support Vector Machine (SVM) with an RBF kernel
4. Artificial Neural Network (ANN / MLP)
5. Convolutional Neural Network (CNN)

The notebook includes dataset exploration, preprocessing, model development, evaluation, confusion matrices, classification reports, learning curves, prediction examples, and a final model comparison.

## Dataset and Evaluation

MNIST contains 70,000 grayscale images of handwritten digits:
- 60,000 original training images
- 10,000 original test images
- Image size: 28 × 28 pixels
- 10 digit classes (0–9)

To keep the five-model experiment manageable, the notebook uses:
- 9,000 training images
- 1,000 validation images
- 2,000 separate test images

All five models use the same partitions to support a fair comparison. The reported test results apply to the selected 2,000-image test sample, not the complete MNIST test set.

## Model Results

| Model | Test accuracy | Correct | Incorrect | Weighted F1 | Validation accuracy |
|---|---:|---:|---:|---:|---:|
| KNN | 94.40% | 1,888 | 112 | 0.9440 | 94.10% |
| Logistic Regression | 90.30% | 1,806 | 194 | 0.9026 | 89.40% |
| SVM (RBF) | 96.10% | 1,922 | 78 | 0.9610 | 95.80% |
| ANN (MLP) | 94.35% | 1,887 | 113 | 0.9436 | 95.10% |
| CNN | **97.65%** | **1,953** | **47** | **0.9765** | **97.50%** |

The CNN was selected as the preferred model because it achieved the highest validation accuracy (97.50%). Its held-out test accuracy was 97.65%.

## Project Files

The final repository is intended to contain:

```text
Handwritten-Digits-Recognition/
├── PRCP_1002_Handwritten_Digits_Recognition_FINAL.ipynb
├── Handwritten_Digits_Recognition_Technical_Report.pdf
├── README.md
├── requirements.txt
└── .gitignore
```

The MNIST dataset is loaded through `tensorflow.keras.datasets.mnist`. It is not stored in this repository.

## Environment

The saved notebook execution recorded these versions:

- NumPy: 2.5.4
- pandas: 3.1.1
- scikit-learn: 1.9.1
- TensorFlow: 2.21.0
- Matplotlib: 3.11.2

The recorded execution used TensorFlow on the CPU. Execution time may differ depending on the computer and software environment.

## Setup

Use a compatible Python environment, then run:

```bash
python -m venv .venv
```

On Windows, activate it with:

```bash
.venv\Scripts\activate
```

Install the project dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `PRCP_1002_Handwritten_Digits_Recognition_FINAL.ipynb`.

The notebook downloads MNIST through Keras when the dataset is not already available locally, so an internet connection may be needed on the first run.

## Limitations

- The experiment uses selected subsets rather than the complete MNIST training and test datasets.
- MNIST images are small, centered grayscale digits and may not represent real-world scanned documents.
- Results may vary with different data samples, random splits, hardware, and software versions.
- The models have not been deployed or tested in a production application.

## Future Improvements

- Train and evaluate using the complete MNIST dataset.
- Test on external handwriting images from different writers.
- Explore data augmentation and image-cleaning techniques.
- Perform systematic hyperparameter tuning.
- Build an application or API for image-based digit prediction.
- Evaluate inference speed and reliability on the intended deployment hardware.

## References

1. LeCun, Y., Cortes, C. and Burges, C. J. C. — [The MNIST Database of Handwritten Digits](http://yann.lecun.com/exdb/mnist/).
2. [TensorFlow MNIST dataset documentation](https://www.tensorflow.org/api_docs/python/tf/keras/datasets/mnist).
3. [scikit-learn documentation](https://scikit-learn.org/stable/).
4. [TensorFlow/Keras Sequential model documentation](https://www.tensorflow.org/guide/keras/sequential_model).
5. [NumPy documentation](https://numpy.org/doc/).
6. [pandas documentation](https://pandas.pydata.org/docs/).
7. [Matplotlib documentation](https://matplotlib.org/stable/).
8. [Python documentation](https://docs.python.org/3/).

## AI Assistance Disclosure

ChatGPT was used as a learning and development assistant to explain machine-learning concepts, review notebook structure, troubleshoot coding issues, improve evaluation methodology, and refine project documentation. Model implementations were executed and evaluated in the project environment. The project author is responsible for understanding, checking, and explaining the code, methodology, and results.
