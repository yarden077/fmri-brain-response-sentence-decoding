# fmri-brain-response-sentence-decoding
# Neural-Language Brain Mapping  
Decoding fMRI with Named-Entity & Sentiment Features

This repository hosts the code and analyses for our project on **how specific linguistic features—named entities and emotional valence—shape neural activity** measured with fMRI.  
We combine the datasets of **Pereira et al. (2018)** and **Tuckute et al. (2024)** with classic (GloVe / fastText) and contextual (BERT) embeddings.

---

## 1  Project Highlights
| Topic | What we did | Key takeaway |
|-------|-------------|--------------|
| **Neural decoding** | Replicated Pereira’s word-/sentence-decoding pipeline; compared GloVe, fastText, and BERT | BERT ↓ average rank by >40 % |
| **Named entities** | Ran spaCy NER on 2 000 sentences; t-tested entity vs. no-entity; ROI-wise stats | Sentences with entities ↑ BOLD (T=22.57, p\<0.001) |
| **Entity type effects** | OLS per ROI with one-hot entity types | PERSON/ORG drive IFG, LANGUAGE drives anterior temporal |
| **Sentiment** | RoBERTa valence vs. human ratings; brain response by sentiment | Negative > Neutral ≈ Positive |

See our paper in `Neural Responses to Linguistic Features: Named Entities and Sentiment Analysis.pdf` for full results.

---

## 2  Repository Layout
├── project.ipynb               # Structured (Pereira) analyses
├── open_ended.ipynb        # Open-ended (Tuckute) analyses
└── README.md                   


*Embedding txt files and raw fMRI matrices are **not** pushed to GitHub for size/privacy.*

---

## 3  Quick Start
Clone and install requirements:

```bash
git clone https://github.com/<USER>/neural-language-brain-mapping.git
cd neural-language-brain-mapping
pip install -r requirements.txt
python -m spacy download en_core_web_trf   # for NER
