# ItsAllGoodMan@LT-EDI-2025: Caste and Migration Hate Speech Detection

Official repository for our submission to the **LT-EDI@LDK 2025 Shared Task on Caste and Migration Hate Speech Detection**, where our team **secured 6th place**.

---

## 🧠 Abstract

Caste and migration hate speech detection is essential for maintaining inclusive online discourse in multilingual regions like India. We propose a hybrid system combining **TF-IDF vectors** and **MuRIL embeddings**, trained with various **machine learning classifiers**, achieving a **macro F1 score of 0.802** on the test set.


---

## 🧱 Methodology Workflow

![Workflow](https://github.com/user-attachments/assets/6fa7a592-2609-45a1-ab23-e6397b261e46)

*Figure: Preprocessing, Feature Extraction (TF-IDF + MuRIL), ML Classification*

---

## 📁 Repository Structure

```

├── models/                       # Scripts for training & evaluation
├── notebooks/                    # Experimental notebooks
├── paper.pdf                     # Final submitted paper
└── README.md

````

---

## 🔄 Preprocessing Steps

To handle the multilingual, code-mixed dataset, we performed:

- **Hashtag segmentation**: Hashtags were split into meaningful tokens using a segmentation model.
- **User mention anonymization**: All `@user` tags were replaced with `<USER>`.
- **Emoji to text**: Emojis were converted into textual descriptions using the `emoji` library.
- **Whitespace normalization**: Removed extra spaces and newline characters.
- **Combined processed hashtags**: After segmentation, hashtags were merged back into the text.

These steps helped reduce noise and retain meaningful semantics in text.

---

## 🧪 Experimental Setup

### 🧩 Feature Extraction

- **TF-IDF Vectors**: Captured token frequency importance.
- **MuRIL Embeddings**: Provided multilingual contextual representations.
- **Hybrid (TF-IDF + MuRIL)**: Combined features yielded the best results.

### ⚙️ Classifiers Evaluated

- Individual: `Random Forest`, `XGBoost`, `SVM`, `Logistic Regression`, `LightGBM`
- Ensemble: `Soft Voting Classifier`, `Hard Voting`, `Stacking (LogReg as meta-model)`

---

## 📊 Key Findings

- TF-IDF alone captured term-frequency-based signals effectively.
- MuRIL embeddings understood semantic nuances in Tamil, English, and code-mixed text.
- **Combining both** led to the best macro F1 score of **0.802**.
- **Soft Voting Classifier** using TF-IDF + MuRIL outperformed all individual models.
- Contextual + statistical features were complementary, especially in noisy, multilingual text.

---



## 🙌 Acknowledgements

Thanks to the organizers of the [LT-EDI@LDK 2025 Shared Task](https://codalab.lisn.upsaclay.fr/competitions/21884).


