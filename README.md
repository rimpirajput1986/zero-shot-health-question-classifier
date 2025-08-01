# Zero-Shot Classification of COVID Health Questions

This project is to explore how pre-trained transformer models can be used to classify real-world COVID-related health questions without task-specific training. The project uses Hugging Face’s `zero-shot-classification` pipeline with questions from the [COVID-Q dataset](https://github.com/JerryWei03/COVID-Q).

Although the dataset includes fine-grained labels, this project maps them into broader categories and uses them only for evaluation — no model fine-tuning was performed.

## Objective

To better understand how zero-shot classification works using large pre-trained language models, and to apply it to real text data without supervised training or annotation effort.

## Dataset

- **Source**: COVID-Q dataset (Wei et al., 2021)
- **Content**: ~1,690 de-identified health-related questions about COVID-19
- **Labeling Approach**:
  - Original labels were fine-grained (e.g., “Symptoms - Respiratory”)
  - Mapped into 6 broader evaluation categories:
    - `Symptoms`, `Testing`, `Treatment`, `Social Impact`, `Information`, `Other`

## Method

1. **Preprocessing**
   - Filtered out incomplete entries
   - Extracted the broad category prefix from each label
   - Mapped them into 6 grouped evaluation categories

2. **Zero-Shot Classification**
   - Used Hugging Face’s `pipeline()` with `facebook/bart-large-mnli`
   - Provided candidate category labels for each question
   - Model returned the top label based on entailment scores

3. **Evaluation**
   - Compared model-predicted label to grouped label for each question
   - Used simple accuracy as the evaluation metric

## Results

- The model's predictions often aligned with grouped categories, particularly for straightforward questions (e.g., about symptoms or testing)
- Overall accuracy was reasonable for a zero-shot setup with no fine-tuning
- Label phrasing and semantic overlap affected predictions noticeably
- This project served as a practical introduction to using LLMs for basic classification tasks

## What I Learned

- How to apply Hugging Face’s zero-shot classification tools
- The importance of candidate label phrasing
- How to repurpose labeled data for evaluation without training
- How zero-shot models behave in real-world health Q&A contexts

## Tools Used

- Python
- Hugging Face Transformers
- Pandas
- Jupyter Notebook / Google Colab

## Next Steps

This was a learning-focused project. Future directions might include:
- Testing multi-label classification
- Fine-tuning on a subset of the labeled dataset
- Expanding candidate label sets or refining phrasing
