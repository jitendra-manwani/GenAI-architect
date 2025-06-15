
# Real-Time Market Sentiment Analyzer using LangChain & Azure OpenAI

This project implements a **LangChain-based pipeline** that takes a company name as input, fetches relevant news from Yahoo Finance, and uses **GPT-4o (via Azure OpenAI)** to generate a structured sentiment analysis JSON.

---

## 🚀 Features

- Accepts company name as input.
- Extracts stock ticker (e.g., MSFT for Microsoft).
- Fetches latest news using Yahoo Finance RSS.
- Uses GPT-4o to classify sentiment, extract entities, and return structured JSON.
- Implemented using LangChain for chaining prompt logic.

---

## 🛠️ Tech Stack

- Python 3.10+
- LangChain
- Azure OpenAI (GPT-4o or GPT-4o-mini)
- Yahoo Finance RSS (via `feedparser`)
- Google Colab (recommended)

---

## 🧪 Setup Instructions

1. **Clone or open notebook in Google Colab**

2. **Install dependencies**

```python
!pip install langchain openai feedparser yfinance
```

3. **Set your credentials**

In the notebook, set the following environment variables:

```python
import os

os.environ["AZURE_OPENAI_API_KEY"] = "<your-azure-openai-api-key>"
os.environ["AZURE_OPENAI_ENDPOINT"] = "<your-azure-endpoint-url>"
os.environ["AZURE_OPENAI_DEPLOYMENT_NAME"] = "<your-deployment-name>"

os.environ["OPENAI_API_TYPE"] = "azure"
os.environ["OPENAI_API_VERSION"] = "2024-02-15-preview"
```

---

## 📌 Usage

1. Run the notebook step-by-step.
2. Enter the company name (e.g., `Microsoft Corporation`) when prompted.
3. The notebook will:
   - Find the stock ticker (e.g., MSFT)
   - Fetch the top 5 latest news from Yahoo Finance
   - Analyze the sentiment using GPT-4o
   - Output structured JSON.

---

## 📤 Sample Output (Structure)

```json
{
  "company_name": "Microsoft Corporation",
  "stock_code": "MSFT",
  "newsdesc": "Microsoft launches new AI services for enterprise users.",
  "sentiment": "Positive",
  "people_names": ["Satya Nadella"],
  "places_names": ["Redmond"],
  "other_companies_referred": ["OpenAI"],
  "related_industries": ["Technology", "Cloud"],
  "market_implications": "Positive outlook for enterprise adoption of AI tools.",
  "confidence_score": 0.93
}
```

---

## ✅ Completed Steps (in this version)

- [x] Step 1: Accept company name
- [x] Step 2: Extract stock code
- [x] Step 3: Fetch news via RSS
- [x] Step 4: Format summaries
- [x] Step 5: Analyze using LangChain + Azure OpenAI

---

## 📎 Notes

- Make sure your Azure deployment supports GPT-4o or GPT-4o-mini.
- If no news appears, try using a well-known stock ticker (like `AAPL`, `MSFT`, `GOOGL`).
