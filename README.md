# BBC News Classification and Summarization Using IBM Granite

## Project Overview
This project applies IBM's Granite 3.3 large language model (LLM) to automate the classification and summarization of BBC news articles. It performs two core Natural Language Processing (NLP) tasks:

1. **Text Classification** — Predict the category of each article (business, entertainment, politics, sport, or tech).
2. **Text Summarization** — Generate concise, 2–3 sentence summaries of the article content.

The project uses a zero-shot approach with prompt engineering and parameter tuning to improve model accuracy and output quality.

## Raw Dataset
- **Name**: BBC Articles Dataset  
- **Source**: [Kaggle – jacopoferretti/bbc-articles-dataset](https://www.kaggle.com/datasets/jacopoferretti/bbc-articles-dataset)

## Output Files
- `output/classification_results.csv`: Ground truth and model predictions for classification
- `output/sample_summaries.txt`: Generated summaries for 5 random articles
  
## Insight & Findings
- **Classification Accuracy (after tuning):** ~80%  
- Most misclassifications occurred between semantically related categories (e.g., business vs. politics).
- Summaries generated before tuning were overly detailed; after tuning, they became more focused and aligned with the expected 2–3 sentence structure.
- A validation loop was added to ensure the model returned valid labels from the allowed category list.

## AI Support Explanation
This project uses IBM’s Granite 3.3 model (via Replicate API) for:
- **Text Classification** using structured prompts and tuned parameters to output clean, one-word labels.
- **Summarization** using free-form generation constrained by max token limits and prompt instructions.

The model is accessed directly in Google Colab through the `langchain_community.llms.Replicate` interface, with prompt refinement inspired by Lab 1 and Lab 2 best practices.
