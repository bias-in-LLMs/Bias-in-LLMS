# Bias in Large Language Models (LLMs)

This repository presents our research on **implicit and intersectional bias in Large Language Models (LLMs)**. The work aligns with the ICWSM community’s focus on computational social science, contributing a structured evaluation of bias across multiple LLMs under persona-driven and neutral conditions.

---

## 📂 Repository Structure
# Bias in Large Language Models (LLMs)

This repository presents our research on **implicit and intersectional bias in Large Language Models (LLMs)**. The work aligns with the ICWSM community’s focus on computational social science, contributing a structured evaluation of bias across multiple LLMs under persona-driven and neutral conditions.

---

## 📂 Repository Structure

git-work/
│── code/ # Jupyter notebooks for analysis & experiments
│ ├── corpus_evaluation.ipynb
│ ├── task1.ipynb
│ └── Task_2.ipynb
│
│── corpus/ # Dataset used for experiments
│ └── corpus.csv
│
│── LLM responses/ # Raw model outputs (Task 1 & Task 2)
│ ├── Task 1/
│ └── Task 2/
│
│── outputs/ # Processed results & bias score calculations
│ ├── corpus-1.xlsx
│ ├── task1_bias_scores_with_synthetic.csv
│ └── task2_bias_scores.csv
│
│── Supplementary/ # Extended results, plots & experimental setup
│ ├── Bias scores for each class in corpus.pdf
│ ├── Corpus_scores_for each sentence.pdf
│ ├── experimental setup, hyperparameters and error bars.pdf
│ ├── Task 1 per prompt score.pdf
│ └── task 2_per-prompt-persona-LLM score.pdf
│
│── prompts-task1.txt # Task 1 prompt list
│── Persona&Prompt-task2.txt # Task 2 personas & prompts

yaml
Copy code

---

## 🧩 Research Overview

Recent work in computational social science (e.g., at ICWSM) has highlighted challenges of **fairness, bias, and representation** in LLMs. Building on this, we design a **two-task framework**:

1. **Task 1 – Intersectional Bias in Prompts**  
   - We introduce a corpus that combines **social categories** (e.g., gender, race, age, disability, class, culture).  
   - LLMs are probed with prompts spanning these intersections.  
   - Bias is quantified at the per-prompt and per-class level.  

2. **Task 2 – Persona-Driven Implicit Bias**  
   - Neutral, Persona A–F conditions are created.  
   - LLMs are tasked with generating responses under **persona influence**.  
   - Differences between neutral vs. persona-driven responses reveal **implicit bias tendencies**.  

Models evaluated include **GPT, Claude, LLaMA, Gemma, and DeepSeek**.

---

## 📊 Outputs

- **Bias Scores**: CSV/Excel files summarizing model bias scores across prompts and personas.  
- **Visualizations & Supplementary PDFs**: Detailed charts, error bars, and per-class breakdowns.  
- **Reproducible Notebooks**: End-to-end Jupyter notebooks for running experiments, scoring responses, and analyzing results.  

---

## 🚀 Usage

1. Clone the repository:
   ```bash
   git clone <repo-link>
   cd git-work
   ```
Install dependencies (Python 3.9+ recommended):

```bash
Copy code
pip install -r requirements.txt
```
Open notebooks in Jupyter:

```
jupyter notebook code/task1.ipynb
```
Explore:

corpus/ → input dataset

LLM responses/ → model outputs

outputs/ → computed bias metrics

🔍 Key Contributions
A novel bias evaluation corpus integrating multiple social categories.

A persona-based framework for surfacing implicit LLM bias.

Comprehensive evaluation across five leading LLMs.

Public release of datasets, code, and results for reproducibility.

📑 Citation
If you use this work, please cite it as:

pgsql
Copy code
@inproceedings{bias-llms-2025,
  title     = {Implicit and Intersectional Bias in Large Language Models},
  author    = {Authors Redacted for Review},
  booktitle = {Proceedings of the International Conference on Web and Social Media (ICWSM)},
  year      = {2025}
}
👥 Acknowledgments
We thank the ICWSM community for ongoing discussions on fairness in LLMs. This project builds upon prior research on bias and computational social science while introducing a novel perspective through intersectional corpus design and persona-driven evaluations.
