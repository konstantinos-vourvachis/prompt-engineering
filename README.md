# Prompt Engineering Lab — Customer Feedback Analysis (Amazon Alexa Reviews)

This repository contains a Jupyter notebook and the datasets needed to run the analysis. It’s set up to be **GitHub-safe** (no real API key stored).

## Repository structure

```
prompt-engineering/
├─ README.md
├─ requirements.txt
├─ prompt-engineering.ipynb
├─ amazon_alexa.tsv
└─ data_amazon.csv
```

- **`prompt-engineering.ipynb`**: the notebook (sanitized — **no real API key stored**)
- **`amazon_alexa.tsv`**: primary dataset used (reviews are in the `verified_reviews` column)
- **`data_amazon.csv`**: included for completeness (present in the workspace), but the core analysis focuses on Alexa reviews

---

## Project overview

We analyze Amazon Alexa customer reviews using only the **top 50 rows** to reduce computation time. The notebook combines prompt-based generation and classic text analysis to answer:

1) **Common themes / product aspects** mentioned in feedback  
   - Prompting approach: **zero-shot** + **few-shot** examples  
   - Supporting analysis: word cloud / frequency-based exploration

2) **Sentiment classification** into **positive / negative / neutral**  
   - Includes a **baseline sentiment method** in the notebook  
   - Also demonstrates **prompt-based** (zero/few-shot) sentiment classification examples

3) **Feature requests / suggestions extraction** (prompted generation)  
   - If no request is present, the notebook instructs the model to output: **`No request mentioned.`**

---

## Key findings (top 50 Alexa reviews)

### Common themes / aspects
Recurring themes include:
- Voice recognition accuracy/responsiveness
- Battery life / power
- Ease of setup / usability
- Sound quality
- Integration with other devices/services
- Design / aesthetics

### Sentiment distribution (top 50)
The sampled top 50 reviews skew strongly positive, with a small number of negative/neutral cases.  
Negative feedback most often references connectivity, voice recognition accuracy, and battery performance.

### Feature requests / suggestions
Common requests include:
- Improve voice recognition (noise/accent handling)
- Improve battery life
- Improve compatibility/integration with other smart devices
- Some reviews contain **`No request mentioned.`**

---

## How to run

### 1) Install dependencies

```bash
pip install -r requirements.txt
```

### 2) Start Jupyter

```bash
jupyter notebook
```

Open: **`prompt-engineering.ipynb`**

---

## OpenAI API Key (security)

Some sections of the notebook use the OpenAI client. **This repository does not include any real API key.**

Set your own key as an environment variable named `OPENAI_API_KEY`:

### macOS / Linux

```bash
export OPENAI_API_KEY="YOUR_KEY_HERE"
jupyter notebook
```

### Windows (PowerShell)

```powershell
setx OPENAI_API_KEY "YOUR_KEY_HERE"
```

**Do NOT commit API keys to GitHub.** If you ever exposed a key in a public repo (even briefly), revoke/rotate it immediately.

---

## Notes on file paths

The notebook expects the datasets to be in the **repo root** (same folder level as the notebook), with these filenames:
- `amazon_alexa.tsv`
- `data_amazon.csv`
