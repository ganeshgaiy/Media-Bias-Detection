# Political Ideology Detection Using BERT

## Introduction
This project focuses on leveraging Bidirectional Encoder Representations from Transformers (BERT) to detect subtle political ideologies and biases in large-scale textual data, such as news articles and social media posts. The objective is to fine-tune BERT to distinguish between factual content and biased framing, and to identify ideological stances in texts.

---

## Motivation
- **Address Polarization:** In an increasingly polarized political climate, understanding biases can mitigate misinformation.
- **Transparency in Media:** Aid journalists and organizations in promoting objective reporting.
- **Impact on Democracy:** Study how media framing affects public opinion and democratic processes.

---

## Objectives
- **Bias Classification:** Detect informational and lexical biases.
- **Stance Detection:** Identify ideological stances (Pro, Neutral, Anti) toward specific entities.
- **Improve Model Performance:** Enhance fine-tuning of BERT for nuanced political discourse analysis.

---

## Datasets
### 1. BASIL Dataset
- **Source:** Annotated for informational and lexical biases.
- **Content:** 300 articles from Fox News, New York Times, and Huffington Post.
- **Annotations:** 1,727 spans for bias with polarity (Positive/Negative).

### 2. PoliticalTweets Dataset
- **Source:** HuggingFace.
- **Content:** 190,491 tweets labeled with stances toward Democrats or Republicans.

### Preprocessing
- Addressed missing metadata.
- Standardized text format and labels.
- Augmented BASIL dataset by splitting articles into labeled sentences.

---

## Methodology
- **Model:** Fine-tuned `bert-base-uncased` for stance detection and bias classification.
- **Task:**
  - Article-level and sentence-level predictions.
- **Training Configuration:**
  - Learning Rate: `2e-5`
  - Optimizer: `AdamW`
  - Batch Size: 8 (BASIL) / 64 or 512 (PoliticalTweets)

---

## Experimental Results
### Article-Level Prediction
- **Performance:** Accuracy of ~40-45%.
- **Challenge:** Model biased toward the majority class (Center).

### Sentence-Level Prediction
- **Observation:** Low validation accuracy (~53-55%) due to lack of stance clarity in individual sentences.

### PoliticalTweets Dataset
- **Performance:**
  - Validation Accuracy: 88.43%
  - Test Accuracy: 87.52% (batch size 64, 4 epochs).
  - Improved generalization with richer data.

---

## Evaluation Metrics
1. **Stance Detection:** Accuracy, Precision, Recall, F1-score (macro-averaged).
2. **Informational Bias Identification:** Sentence-level and token-level precision, recall, and F1-score.

---

## Challenges
- Overfitting due to small dataset size.
- Class imbalance affecting minority stance predictions.

---

## Future Work
- Incorporate larger datasets like SemEval2016 and Elections2016.
- Experiment with additional datasets for better generalization.
- Address overfitting using advanced regularization techniques.

---

## Acknowledgements
- **Contributors:** Ganesh Gaiy, Vittal Siddaiah, Dayuan Chen.
- **References:** BASIL Dataset (Fan et al., 2019), PoliticalTweets Dataset (HuggingFace).

---

## License
This project is licensed under the MIT License.
