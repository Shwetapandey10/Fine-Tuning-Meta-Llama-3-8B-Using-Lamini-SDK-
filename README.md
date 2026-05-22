# Fine-Tuning Meta Llama 3 (8B) Using Lamini SDK

This project demonstrates how to fine-tune a Large Language Model (LLM) using the Lamini Python SDK with the **Meta-Llama-3-8B-Instruct** model. It includes custom dataset creation, model initialization, and fine-tuning with configurable hyperparameters.

---

## Project Description

In this project:
- A custom **Question–Answer dataset** is created
- The `meta-llama/Meta-Llama-3-8B-Instruct` model is initialized using Lamini
- The model is fine-tuned using domain-specific training data
- Hyperparameters such as learning rate are configured for optimization

---

## Tech Stack

- Python
- Lamini SDK
- Meta Llama 3 (8B Instruct)
- LangChain
- Streamlit
- Neo4j

---

## Project Structure

```
├── finetune.py
├── requirements.txt
└── README.md
```

---

## Dataset Format

The dataset is structured as input-output pairs:

```json
{
    "input": "User question",
    "output": "Expected answer"
}
```

This format helps the model learn instruction-based responses effectively.

---

## Installation & Setup

**Clone the Repository**
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

**Create a Virtual Environment (Optional but Recommended)**
```bash
python -m venv venv
```

Activate on Windows:
```bash
venv\Scripts\activate
```

Activate on Mac/Linux:
```bash
source venv/bin/activate
```

**Install Dependencies**
```bash
pip install -r requirements.txt
```

---

## API Key Configuration

> **Do NOT hardcode your API key in the script!**

Set your Lamini API key as an environment variable:

Windows:
```bash
set LAMINI_API_KEY=your_api_key_here
```

Mac/Linux:
```bash
export LAMINI_API_KEY="your_api_key_here"
```

Then update the script:
```python
import os
lamini.api_key = os.getenv("LAMINI_API_KEY")
```

---

##Running the Script

```bash
python finetune.py
```

The script will:
- Create training data
- Initialize the model
- Fine-tune the model
- Apply hyperparameter configuration

---

## Hyperparameters Used

```python
finetune_args = {
    'learning_rate': 1.0e-4
}
```

You can experiment with:
- `learning_rate`
- `max_steps`
- `early_stopping`
- `optim` (e.g. `adam`, `sgd`)

---

## Learning Outcomes

- Understanding the LLM fine-tuning process
- Creating structured datasets for training
- Configuring hyperparameters
- Working with Generative AI APIs

---

## Future Enhancements

- Load dataset from external JSON/CSV file
- Add model evaluation metrics
- Build UI using Streamlit
- Deploy as an API service

---

