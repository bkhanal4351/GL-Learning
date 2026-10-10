# DualLens Analytics

I built this project to rank five tech companies (GOOGL, MSFT, IBM, NVDA, AMZN) by looking at them through two lenses: their financial numbers and their AI initiatives.

## Steps

1. I pulled three years of stock prices and key metrics from Yahoo Finance and charted them.
2. I loaded the company PDFs, split them into chunks and stored them in a ChromaDB vector store.
3. I built a retrieval Q&A function that answers only from the retrieved text and says "I don't know" otherwise.
4. I tested it with five question types and scored the answers with three judge prompts.
5. I measured accuracy on a 20 question gold set, then used DSPy GEPA to improve the prompt and checked it on 8 held out questions.
6. I ranked the companies using both lenses and gave the result a confidence score and a routing verdict.

## Results

Held out accuracy went from 25% to 62%. The final confidence was 76.5 out of 100, so the ranking was flagged for review.

## How to run

1. Open `DualLens_Analytics.ipynb` in Google Colab.
2. Upload `Project_Datafiles.zip` and a `config.json` (copied from `config.example.json` with your API key and base URL).
3. Run all cells.

The full output is in `DualLens_Analytics.html`.
