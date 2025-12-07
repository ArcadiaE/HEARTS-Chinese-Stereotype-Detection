# Beyond English: Adapting HEARTS for Holistic Chinese Stereotype Detection

**Coursework 2: AI for Sustainable Development**
**Student Number:** 22003632
**Institution:** University College London

## Project Overview

This project replicates and contextualizes the HEARTS framework (originally designed for English text stereotype detection) to the Chinese social media landscape. By adapting the model to handle linguistic complexities such as high-context sarcasm and homophones, this work addresses the limitations of existing English-centric models in detecting culturally specific biases.

The system utilizes the COLD (Chinese Offensive Language Dataset) and employs a "Green AI" strategy via Partial Unfreezing to align with Sustainable Development Goals (SDGs), specifically targeting Reduced Inequalities (SDG 10) and Gender Equality (SDG 5).

## Methodology

### Model Architecture
- **Backbone:** bert-base-chinese (Hugging Face Transformers)
- **Tokenization:** Character-level tokenization to capture the semantic depth of Chinese characters (Hanzi).
- **Optimization Strategy:** Partial Unfreezing. We froze the bottom 8 layers of the BERT encoder and fine-tuned only the top 4 layers and the classifier head. This reduced trainable parameters by approximately 70 percent.

### Dataset
- **Source:** COLD (Chinese Offensive Language Dataset)
- **Size:** 37,480 labeled sentences
- **Categories:** Race/Ethnicity, Gender, and Regional discrimination.
- **Split:** 80% Training, 20% Testing.

## Key Features

1. **Contextual Adaptation:** Successfully migrated the HEARTS framework to a non-Latin script language, addressing specific Chinese regional and gender stereotypes.
2. **Explainability:** Integrated SHAP (SHapley Additive exPlanations) to provide token-level transparency, allowing for the visualization of which characters contribute most to the stereotype classification.
3. **Sustainability:** The Partial Unfreezing technique significantly lowers the computational cost and carbon footprint of training, aligning with SDG 12 (Responsible Consumption and Production).

## Results

The adapted model achieves state-of-the-art performance, outperforming the baseline English transfer models.

| Metric | Score |
| :--- | :--- |
| **F1-Score** | 0.9027 |
| **Accuracy** | 90.27% |
| **Validation Loss** | 0.267 |

## Installation and Usage

### Prerequisites
- Python 3.8 or higher
- PyTorch with CUDA support (recommended)

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone [https://github.com/YourUsername/AISD-CW2-Chinese-Stereotype-Detection.git](https://github.com/YourUsername/AISD-CW2-Chinese-Stereotype-Detection.git)
   cd AISD-CW2-Chinese-Stereotype-Detection
