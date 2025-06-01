# Classification-of-breast-cancer

- Classification of breast cancer by using machine learning is an essential field of research is to improve the early identification and prognosis of breast cancer.

**Goal**: Predict whether a tumor is **benign** or **malignant**

---

## 📊 Dataset

- wiscosin breast cancer - 699 clinical cases with 11 attributes
  - `sample_code_number` (ID)
  - `class` (malignant or benign)
  - 9 clinical attributes
-**Class distribution**:  
  - 241 Benign  
  - 458 Malignant

---

## 🧹 Pre-processing

- No null values, but 16 rows had `'?'` in the “Bare Nuclei” column → removed using a mask.
- A redundant header row was created after filtering → dropped.
- Data types were initially `object` → converted to `int`.
- Dropped the `sample_code_number` (not useful for classification).
- Final dataset: **683 rows** × **10 attributes**.

---

### 📋 Dataset Summary and Class Distribution

| Description                               | Value        |
|-------------------------------------------|--------------|
| Original clinical cases                   | 699          |
| Original attributes                       | 11           |
| Rows with `?` in “Bare Nuclei”            | 16           |
| Final cleaned dataset                     | 683          |
| Final attributes (after dropping ID)      | 10           |
| **Benign cases**                          | **241**      |
| **Malignant cases**                       | **458**      |

---

## 📋 Segregating Dataset

- **Y** – “class” attribute ( Output/ Dependent variable )
- **X** – other 9 attributes except “class” ( Input/Independent variable )

---

## 🔀 Splitting Dataset

- Training set - **60%**
- Testing set - **40%**

---

## Classifiers used

- Regularized logistic regression with LASSO using General linear model
- SVM with RBF kernel
- Artificial Neural Network (ANN) with a single hidden layer
- SVM with linear kernel
- Softmax discriminant classifier
- Fuzzy c means clustering
- Distance to mean classifier

---

## 📈 Evaluation:

- **Accuracy**, **Sensitivity** and **Specificity** for all models except Fuzzy c means clustering.

    ### 🔁  Ensembling

        - Ensembling is a technique used to improve model performance by combining predictions from multiple models. This project implements both:

            - Soft Voting: Averages the predicted probabilities from individual classifiers and chooses the class with the highest average probability.
            - Hard Voting: Uses the majority class predicted by the classifiers.

        - Both approaches showed improvement in overall classification performance. Hard voting achieved a slightly higher sensitivity compared to soft voting, making it more suitable for prioritizing malignant case detection.

- **Fuzzy Partition Coefficient(FPC)** for Fuzzy c means clustering (We cannot get Accuracy, Sensitivity and
Specificity directly as it is an unsupervised algorithm.)

---

### 🛠️ Tools and Libraries Used

The following tools and libraries were used throughout the project:

- **Python**
- **NumPy** – for numerical operations
- **Pandas** – for data preprocessing and manipulation
- **Scikit-learn** – for machine learning models and metrics
- **Matplotlib** – for visualizing results
- **Seaborn** – for enhanced data visualization
- **SciPy** – for statistical operations and clustering
- **Jupyter Notebook** – for coding and documenting the workflow

All experiments were conducted in a Jupyter Notebook environment to allow interactive exploration, tuning, and comparison of models.

---

## 📊 Results from Referenced Article

| Model               | Accuracy | Specificity | Sensitivity |
| ------------------- | -------- | ----------- | ----------- |
| Logistic Regression | 0.95     | 0.87        | 0.99        |
| SVM (RBF)           | 0.96     | 0.96        | 0.97        |
| ANN                 | 0.94     | 0.84        | 0.99        |

|        | Accuracy | Specificity | Sensitivity |
| ------ | -------- | ----------- | ----------- |
| Voting | 0.97     | 0.95        | 0.99        |

---

## 📊 Results from Same Implementation (This Project)

| Model               | Accuracy | Specificity | Sensitivity |
| ------------------- | -------- | ----------- | ----------- |
| Logistic Regression | 0.9416   | 0.98        | 0.89        |
| SVM (RBF)           | 0.9562   | 0.95        | 0.97        |
| ANN                 | 0.9635   | 0.96        | 0.97        |

| Ensemble Type | Accuracy | Specificity | Sensitivity |
| ------------- | -------- | ----------- | ----------- |
| Soft Voting   | 0.9562   | 0.95        | 0.96        |
| Hard Voting   | 0.9562   | 0.95        | 0.97        |

---

## 📊 Results for Other Models

| Model                    | Accuracy    | Specificity | Sensitivity |
| ------------------------ | ----------- | ----------- | ----------- |
| Softmax Discriminant     | 0.9562      | 0.95        | 0.96        |
| LDA                      | 0.9416      | 0.97        | 0.89        |
| SVM                      | 0.9635      | 0.95        | 0.98        |
| Distance to Mean         | 0.9240      | 0.96        | 0.85        |
| Fuzzy C-Means Clustering | FPC: 0.8296 | -           | -           |

---

## Conclusion 

- **ANN** achieved the highest **accuracy** among all tested models.
- **SVM (RBF)** and **ensemble methods** also performed very well.
- Proper preprocessing and careful model selection significantly improved classification performance.

---

## 👩‍💻 Author

- **Venuja Shanmugarajah**  

---
