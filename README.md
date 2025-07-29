# Zero-Shot Classification of Health-Related Questions with BART and RoBERTa

I built a zero-shot text classification pipeline to categorize health-related questions about COVID-19 using transformer-based models. Specifically, I evaluated two pre-trained Natural Language Inference (NLI) models — facebook/bart-large-mnli and roberta-large-mnli — on the [COVID-Q dataset](https://github.com/JerryWei03/COVID-Q), which contains 1,600+ real-world, de-identified health-related questions. The goal was to classify questions into categories like symptoms, prevention, transmission, and treatment without needing labeled training data.
This project explores how zero-shot learning can help categorize health-related questions in the absence of labeled data, which is especially useful in emerging public health contexts.

---

## Categories Used

For this task, I consolidated detailed question types into six high-level categories to enable more generalizable classification.

- `Symptoms`
- `Testing`
- `Treatment`
- `Social Impact`
- `Information`
- `Other`

---

## Results

| Model                | Top-1 Accuracy | Top-3 Accuracy |
|---------------------|----------------|----------------|
| BART-large-MNLI      | 32.08%         | TBD            |
| RoBERTa-large-MNLI   | 27.74%         | 53.11%         |

The models frequently misclassified abstract or speculative questions (e.g., “Will COVID go away?”) as concrete categories like "Symptoms" or "Testing".

---

## 📦 How to Run

1. Clone the repo
2. Install dependencies:
   ```bash
   pip install transformers pandas matplotlib

