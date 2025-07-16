# Odk2Word
A set of Python notebooks to convert ODK/KoBo/SurveyCTO XLSForms into well-formatted Word documents. Supports question labels, choices, constraints, relevance logic, and multilingual export (e.g., English and Bangla). Designed for researchers, M&amp;E professionals, and survey implementers to easily generate print-ready survey tools.

# ODK/KoBo/SurveyCTO XLSForm to Word Converter
This repository provides three Python notebooks to automatically convert XLSForms (used in ODK, KoBoToolbox, and SurveyCTO) into well-formatted Word documents for survey printing or review.

---
## 🔧 Notebooks Included
| Notebook | Description |
|----------|-------------|
| `Odk2Word.ipynb` | Basic exporter: outputs **Variable, Question, Choices** |
| `Odk2Word_Con_Rel.ipynb` | Outputs **Variable, Question, Choices, Constraint, Relevance** |
| `Odk2WordAll.ipynb` | Multilingual exporter: generates **separate Word files** for each language in `label::language` columns |
---

## 📁 Input Requirements
All scripts require an **XLSForm** with the following:
- **Sheet: `survey`**
  - Columns: `type`, `name`, `label` or `label::English`, `label::Bangla`, etc.
  - Optional: `constraint`, `relevance`
- **Sheet: `choices`**
  - Columns: `list_name`, `value`, `label` or `label::English`, `label::Bangla`, etc.
---

## 🚀 How to Use
### ✅ Option 1: Use in Google Colab (No installation needed)
1. Go to [https://colab.research.google.com](https://colab.research.google.com)
2. Upload and open one of the notebooks:
   - `Odk2Word.ipynb`
   - `Odk2Word_Con_Rel.ipynb`
   - `Odk2WordAll.ipynb`
3. Upload your XLSForm when prompted
4. Output Word files will automatically download

> ⚠️ Colab does not auto-save output — make sure to download before closing.
---

### ✅ Option 2: Use on Your Local Machine
#### 1. Clone the Repository
```bash
git clone https://github.com/your-username/odk2word.git
cd odk2word

2. Create a Virtual Environment (Recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

3. Install Required Packages
pip install pandas python-docx

📝 Output Format (in Word)
Each question is shown as a row in a table with:

Variable — question name

Question — question label (in English or Bangla)

Choices — list of options if select_one or select_multiple

Constraint (optional) — validation rules

Relevance (optional) — skip logic / conditional display

Multilingual notebooks generate one Word file per language.


📄 Example
Variable	Question	Choices	Constraint	Relevance
gender	What is your gender?	[1] Male
[2] Female		
age	What is your age?	[Number]	. >= 18	
remark	Other (specify)	[Text]		${choice}=99

📬 Author
Md. Zahirul Islam
Senior Project Associate, ARCED Foundation
📧 zahirul.islam@arced.foundation
📱 +8801688831919
