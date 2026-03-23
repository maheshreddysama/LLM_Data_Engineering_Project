# Data Engineering Pipeline: Smart Data Validation

## Overview
A robust data engineering pipeline designed to ingest, validate, and process customer order data. This project demonstrates how to combine traditional rule-based data quality checks with modern Large Language Model (LLM) validation to handle semi-structured data errors and anomalies.

## Key Features
* **Custom Parsing:** Implements a schema-aware parser to handle CSV formatting issues and comma-delimiters in text fields.
* **Multi-Layer Validation:**
    * **Layer 1 (Deterministic):** Fast rule-based validation using Python/Pandas for standard data quality checks (email format, age validation, price checks).
    * **Layer 2 (Cognitive):** LLM-based validation for non-trivial data anomalies, filtering flagged rows to optimize API usage and costs.
* **Automated Data Quality:** Automatic categorization of clean records vs. quarantine records for manual review.
* **Storage:** Results persisted into a local SQLite database for easy auditability.

## Technology Stack
* **Language:** Python
* **Data Processing:** Pandas
* **API Integration:** OpenRouter (OpenAI-compatible) for cost-efficient LLM access
* **Database:** SQLite
* **Pipeline Logic:** Rule-based heuristics + LLM-based intelligent filtering

## Project Structure
- `orders.csv`: Raw, potentially inconsistent input data.
- `datavalidationusingLLM.ipynb`: The core ingestion, validation, and storage script.
- `pipeline.db`: The processed output database (separate `clean_orders` and `quarantine` tables).

## How to Run
1. Clone this repository.
2. Open `datavalidationusingLLM.ipynb` in Google Colab or Jupyter.
3. Install dependencies: `pip install pandas openai`
4. Set your `OPENROUTER_API_KEY`.
5. Execute the cells to run the validation pipeline.
