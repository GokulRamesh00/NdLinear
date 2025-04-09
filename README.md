# Multi-Modal Document Classification with NdLinear

This project builds a multimodal deep learning model to classify scanned document images by combining both visual (image) and textual (OCR-extracted) features. The model leverages a ResNet backbone for image encoding, BERT for text encoding, and a custom `NdLinear` layer to fuse both modalities effectively.

---

## 📌 Key Features

- ✅ **Multimodal Fusion**: Combines visual (ResNet18) and text (BERT) features
- ✅ **NdLinear Layer**: Replaces traditional FC layers with a more expressive fusion method
- ✅ **OCR Integration**: Extracts text using Tesseract OCR from `.tif`, `.jpg`, etc.
- ✅ **Small Sample-Friendly**: Trains even on low-resource, balanced sample datasets
- ✅ **Flexible Input**: Works on folder-structured datasets (1 folder = 1 class)

---


## 📦 Dataset

The dataset used in this project is derived from the publicly available **RVL-CDIP** dataset on Kaggle.

📂 **Kaggle Dataset:**  
[The RVL-CDIP Dataset (Test)](https://www.kaggle.com/datasets/pdavpoojan/the-rvlcdip-dataset-test?resource=download)

## Model Architecture

```text
                 +----------------+       +----------------+
   image input → |   ResNet18     |       |     BERT       | ← ocr_text
                 +--------+-------+       +--------+-------+
                          |                        |
                          +----------+-------------+
                                     ↓
                            [ ResNet ⬌ BERT ]
                               via NdLinear
                                     ↓
                          Fully Connected Head
                                     ↓
                             Class Probabilities
```

## 🪪 License

This project is open-sourced under the MIT License.

