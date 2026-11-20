# Question Answering (QA) System using BERT

## Project Overview

This project implements an Extractive Question Answering (QA) System using the BERT (Bidirectional Encoder Representations from Transformers) architecture.

The system takes a paragraph (context) and a question as input and predicts the answer directly from the given paragraph.

The project uses the Stanford Question Answering Dataset (SQuAD) to fine-tune a pretrained BERT model.

## Project Objectives

- Understand how BERT works for Question Answering.
- Load and explore the SQuAD dataset.
- Perform text tokenization and preprocessing.
- Convert answer character positions into token positions.
- Fine-tune BERT for extractive question answering.
- Evaluate model performance using Exact Match and F1 Score.
- Test the model with custom questions and contexts.
- Save and reload the trained model.
- Create a Flask API for question answering.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| BERT | Transformer architecture |
| PyTorch | Model training |
| Hugging Face Transformers | Loading BERT and tokenizer |
| Hugging Face Datasets | Loading SQuAD dataset |
| SQuAD | Question Answering dataset |
| NumPy | Numerical operations |
| Pandas | Data handling |
| Flask | API development |
| Google Colab | Development environment |

## Model Architecture

**Model:** BERT Base Uncased

**Pretrained Model:** `google-bert/bert-base-uncased`

The model is fine-tuned for extractive question answering.

It predicts two values:

- Start Position: The token where the answer begins.
- End Position: The token where the answer ends.

The predicted answer is extracted from the original context using these positions.

## Dataset

**Dataset:** Stanford Question Answering Dataset (SQuAD)

**Hugging Face Dataset:** [rajpurkar/squad](https://huggingface.co/datasets/rajpurkar/squad)

The dataset contains:

- Context: A paragraph containing information.
- Question: A question based on the paragraph.
- Answers: The correct answer text and its character position.

For this learning project, a subset of 3,000 training examples and 300 validation examples is used.

## Project Workflow

1. Environment setup and GPU configuration.
2. Dataset loading and exploration.
3. BERT tokenizer and model loading.
4. Text tokenization and preprocessing.
5. Answer start and end position mapping.
6. Dataset conversion into PyTorch tensors.
7. BERT fine-tuning.
8. Model evaluation using Exact Match and F1 Score.
9. Custom question-answering predictions.
10. Model saving and reloading.
11. Flask API creation and testing.

## Example

**Context:**

India is a country in South Asia. New Delhi is the capital of India. The Indian currency is the Indian Rupee.

**Question:**

What is the capital of India?

**Expected Answer:**

New Delhi

## Evaluation Metrics

The model is evaluated using:

**1. Exact Match (EM)**

Measures whether the predicted answer exactly matches the reference answer after text normalization.

**2. F1 Score**

Measures the overlap between the predicted answer and the actual answer using precision and recall.

Note: The model is trained and evaluated on a small subset of SQuAD. The results should not be considered official SQuAD benchmark results.

## Flask API

A simple Flask API is included in the notebook.

It provides two endpoints:

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Checks whether the API is running |
| `/answer` | POST | Accepts a question and context and returns the predicted answer |

Example JSON request:

```json
{
  "question": "What is the capital of India?",
  "context": "India is a country in South Asia. New Delhi is the capital of India."
}
```

## Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Move into the project directory:

```bash
cd BERT-Question-Answering
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## How to Run

1. Open the notebook in Google Colab.
2. Enable GPU from Runtime → Change runtime type → T4 GPU.
3. Install the required dependencies.
4. Execute the notebook cells in order.
5. Load the SQuAD dataset.
6. Fine-tune the BERT model.
7. Evaluate the model.
8. Test custom questions and contexts.
9. Save the trained model.

## Project Files

```text
BERT-Question-Answering/
│
├── Question Answering (QA) System using BERT.ipynb
├── README.md
└── requirements.txt
```

The trained model is saved separately in the `bert_qa_model` directory when the notebook is executed. Model weights are not included in this repository.

## Learning Outcomes

Through this project, I learned:

- How BERT works for extractive question answering.
- How Transformer tokenization works.
- How to preprocess the SQuAD dataset.
- How to map character positions to token positions.
- How to fine-tune a pretrained BERT model.
- How to evaluate Question Answering models.
- How to save and reload trained models.
- How to create a Flask API for an NLP model.

## Future Improvements

- Train using a larger portion of the SQuAD dataset.
- Experiment with additional training epochs.
- Improve answer confidence and no-answer handling.
- Build a user-friendly web interface.
- Deploy the application to a cloud platform.

## Author

Created as a hands-on learning project to understand Transformer-based Natural Language Processing and Question Answering systems.
