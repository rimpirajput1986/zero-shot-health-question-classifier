# Zero-Shot Classification of Health-Related Questions with BART and RoBERTa

This project uses large language models (LLMs) to classify COVID-related health questions into broad categories using **zero-shot learning** — no labeled training data required.

We evaluate two transformer models (`facebook/bart-large-mnli` and `roberta-large-mnli`) on the [COVID-Q dataset](https://github.com/JerryWei03/COVID-Q), which contains 1,600+ real-world, de-identified health-related questions.

---

## Categories Used

We map fine-grained question types to 6 broad categories:

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

1. Clone the repo or open the notebook in [Google Colab](https://colab.research.google.com/)
2. Install dependencies:
   ```bash
   pip install transformers pandas matplotlib

