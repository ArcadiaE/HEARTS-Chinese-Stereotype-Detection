# Beyond English: Adapting HEARTS for Holistic Chinese Stereotype Detection

**Student Name:** Yike Zhang
**Student ID:** 22003632
**Department:** Computer Science, UCL
**Module:** AI for Sustainable Development (Coursework 2)

---

## Project Overview

This project contextualizes the **HEARTS** framework (originally designed for English) to detect stereotypes in **Chinese social media**. By adapting the model to the Chinese linguistic context, this work addresses specific regional and gender biases prevalent in online discourse.

The project utilizes the **COLD (Chinese Offensive Language Dataset)** and implements a **Green AI** strategy (Partial Unfreezing) to ensure the model is both accurate and computationally sustainable.

![Project Poster Overview](poster_overview.png)

## Sustainable Development Goals (SDGs)

This project aligns with the following UN SDGs:
* **SDG 5 (Gender Equality):** Detection of toxic gender stereotypes (e.g., sexism).
* **SDG 10 (Reduced Inequalities):** Mitigating discrimination against marginalized regional groups.
* **SDG 12 (Responsible Consumption & Production):** reducing carbon footprint via parameter-efficient training.

## Methodology

### 1. Model Architecture
* **Backbone:** `bert-base-chinese`
* **Strategy:** Partial Unfreezing (Green AI)
    * **Frozen Layers:** Layers 0-7 (General linguistic features)
    * **Trainable Layers:** Layers 8-11 + Classifier Head (Task-specific features)
* **Tokenization:** Character-based tokenization (Hanzi)

![Model Architecture and Partial Unfreezing](model_architecture.png)

### 2. Dataset
* **Source:** COLD (Chinese Offensive Language Dataset)
* **Size:** 37,480 labeled sentences
* **Categories:** Race, Gender, Region

## Performance Results

The model achieves robust performance, outperforming the baseline English transfer expectations.

| Metric | Value |
| :--- | :--- |
| **F1-Score** | 0.9027 |
| **Accuracy** | 90.27% |
| **Validation Loss** | 0.267 |

### Visualization of Results
The following chart illustrates the training convergence and final performance metrics.

![Performance Metrics](performance_chart.png)

## Explainability (SHAP)

To ensure transparency, we utilize **SHAP (SHapley Additive exPlanations)** to visualize token-level contributions. This allows us to understand which specific Chinese characters or terms triggered the stereotype classification.

![SHAP Analysis Example](shap_analysis.png)

## Installation and Usage

### Requirements
* Python 3.8+
* PyTorch
* Transformers (HuggingFace)
* SHAP

### Run the Project
1.  Clone the repository.
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3.  Execute the Jupyter Notebook:
    ```bash
    jupyter notebook AISD_CW2_ver2.2.ipynb
    ```

## References
1.  *HEARTS: A Holistic Framework for Explainable, Sustainable, and Robust Text Stereotype Detection.*
2.  *COLD: Chinese Offensive Language Dataset.*
