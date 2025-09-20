# Bias in Large Language Models (LLMs)

## Overview

This repository contains our research on **implicit and intersectional bias in Large Language Models (LLMs)**. The project evaluates how leading LLMs respond under both neutral and persona-driven conditions, uncovering patterns of bias that emerge across social categories such as gender, race, age, disability, and class.

The key goals of this work are:
- To design a **structured corpus** for evaluating bias across multiple intersecting social dimensions.  
- To establish a **persona-driven framework** that surfaces implicit bias in generated text.  
- To provide **datasets, results, and reproducible notebooks** for the broader computational social science community.  
- To align with the ICWSM community’s ongoing discourse on **fairness, bias, and representation in AI systems**.  

---

## 📐 Architecture Diagram

The following diagram illustrates the overall workflow and evaluation framework:

![Architecture Diagram](Architecture-Diagram.jpg)


## Repository Structure

The repository is organized into the following components:

```
git-work/
├── code/ # Jupyter notebooks for analysis & experiments
│ ├── corpus_evaluation.ipynb
│ ├── task1.ipynb
│ └── task2.ipynb
│
├── corpus/ # Evaluation corpus
│ └── corpus.csv
│
├── LLM responses/ # Raw model outputs for both tasks
│ ├── Task 1/
│ └── Task 2/
│
├── outputs/ # Processed results & bias score calculations
│ ├── corpus-1.xlsx
│ ├── task1_bias_scores_with_synthetic.csv
│ └── task2_bias_scores.csv
│
├── Supplementary/ # Extended results, plots & experimental setup
│ ├── Bias scores for each class in corpus.pdf
│ ├── Corpus_scores_for each sentence.pdf
│ ├── experimental setup, hyperparameters and error bars.pdf
│ ├── Task 1 per prompt score.pdf
│ └── Task 2 per prompt persona LLM score.pdf
│
├── prompts-task1.txt # List of Task 1 prompts
├── Persona&Prompt-task2.txt # Personas & prompts for Task 2
└── requirements.txt # Dependencies
```

---

## Key Components

### 1. Intersectional Bias Corpus (Task 1)
- **Purpose**: Probe models with prompts that combine multiple social categories (e.g., gender × race, age × disability).  
- **Output**: Bias quantified at both per-prompt and per-class levels.  
- **Notebooks**: `code/task1.ipynb`, `code/corpus_evaluation.ipynb`.

### 2. Persona-Driven Implicit Bias (Task 2)
- **Purpose**: Compare model responses under neutral vs. persona conditions (Persona A–F).  
- **Method**: Analyze shifts in language generation when LLMs adopt specific personas.  
- **Output**: Implicit bias tendencies surfaced through persona influence.  
- **Notebook**: `code/task2.ipynb`.

### 3. Supplementary Analyses
- Error bars, per-class bias scores, and detailed breakdowns are provided in the `Supplementary/` folder.  
- Results span **GPT, Claude, LLaMA, Gemma, and DeepSeek** models.  

## Ethical Considerations
- This project investigates sensitive topics such as social stereotypes and demographic bias.
- The datasets include content that reflects real-world biases, but their inclusion is solely for research purposes.
- The work does not endorse any stereotypical views.
- Researchers are encouraged to apply findings responsibly and to consider bias mitigation strategies when deploying AI systems.

## Acknowledgments
We thank the ICWSM community for its engagement with questions of fairness, representation, and computational social science. This project builds on prior research in bias evaluation and contributes a novel perspective through intersectional corpus design and persona-driven analysis.
