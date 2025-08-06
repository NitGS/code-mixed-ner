# code-mixed-ner

# Code-Mixed NER: Named Entity Recognition on English–Indian Text

This project demonstrates a small-scale multilingual NER pipeline for code-mixed Indian languages (Telugu/Tamil + English). Inspired by internship work at Palmtree Infotech.

## 📊 Dataset
- Hand-annotated sentences mixing English with Telugu/Tamil
- Entity labels: PERSON, LOCATION, ORGANIZATION, FOOD, etc.
- Format: CSV (sentences + annotation spans)

## ⚙️ Tools Used
- fastText (language detection)
- Meta NLLB (translation)
- spaCy (custom NER)
- GLiNER (zero-shot NER)
- HuggingFace Transformers
- Pandas, Python

## 🧪 Sample Output
| Sentence                                      | Entities Detected                                  |
|-----------------------------------------------|----------------------------------------------------|
| "I loved the dosai at Sangeetha, Chennai!"    | FOOD: dosai, ORG: Sangeetha, LOC: Chennai          |

## 🚀 How to Run
1. Clone the repo
2. Navigate to `notebooks/ner_experiments.ipynb`
3. Install dependencies from `requirements.txt`
4. Run the notebook to test entity extraction with spaCy or GLiNER

## 📁 Folder Structure
- `data/`: CSV files with sentences and annotations
- `notebooks/`: Jupyter notebooks with demo pipeline
- `scripts/`: Optional scripts for training/evaluation

## 📌 Disclaimer
This is a public reconstruction of internship work using synthetic data and open-source tools. No proprietary data or internal IP is shared here.
