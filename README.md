# Agentic AI System for ESG Compliance

This repository contains the codebase for the paper:
**"An Agentic AI System for ESG Compliance and Responsible Sustainability Reporting"**.

## 🔍 Overview

This system provides a modular, agent-based AI framework for evaluating ESG (Environmental, Social, and Governance) reports against disclosure standards such as GRI and SASB. It performs:

- **Layout-aware document parsing**
- **Semantic content indexing**
- **Disclosure rule matching**
- **Metadata extraction**
- **Rule-based compliance evaluation**
- **Improvement suggestion generation**

The system is built using a modular, orchestration-agent architecture, supporting explainable and auditable ESG evaluation workflows.

## 🧩 Modules

- `agenticai_final(forgithub).py`: Core functions, LLM prompts, evaluation logic, vector indexing, and metadata extraction.
- `AgenticAI_Final(ForGitHub).ipynb`: Notebook interface for Colab users to execute the pipeline interactively.

## 🛠️ Key Technologies

- LangChain (for orchestration and function-calling tools)
- OpenAI, Anthropic, Gemini APIs
- FAISS for vector search
- Docling for document parsing
- Python 3 (Colab compatible)

## 📦 Usage

### 1. Admin Preparation

Upload and initialize all disclosure standards (GRI + SASB):

```python
admin_prepare_and_save_disclosures_full()
```

This step creates a unified machine-readable disclosure rulebase in `admin/all_disclosures.json`.

---

### 2. ESG Report Evaluation Workflow

```python
# Upload your ESG report
tool_upload_esg_pdf()

# Select ESG frameworks (1 = GRI, 2 = SASB, 3 = Both)
tool_select_framework(choice="3")

# Match disclosures (method = "llm" or "traditional")
tool_run_matching(method="llm")

# Run metadata extraction
run_metadata_extraction(DISCLOSURES, providers, selected_models)

# Evaluate compliance
run_llm_metadata_evaluation(DISCLOSURES, METADATA_BY_MODEL, "gpt", providers["gpt"])

# Generate improvement suggestions
generate_esg_fixes_with_retrieval_multi(EVAL_RESULTS["gpt"], rule_vectorstore, providers, selected_models)
```

---

## 🧠 Citation

> 📌 Citation will be added here once the paper is accepted for publication.

## 🔒 License

This project is licensed under the **MIT License**.
