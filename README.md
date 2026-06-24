# Dadi Translator

Dadi Translator is a simple Streamlit web application for translating Simplified Chinese documents into professional English Word documents.

## Main Purpose

Upload a Chinese document, translate it into English, preview and edit the result, then download a formatted `.docx` file with the Dadi Coach logo.

## Supported File Types

- `.docx`
- `.doc`
- `.txt`
- `.md`

Important note about `.doc`: legacy Microsoft Word `.doc` extraction requires `antiword`. This repository includes `packages.txt` so Streamlit Cloud can install it. If a specific `.doc` file cannot be extracted, convert it to `.docx` and upload again.

## Repository Structure

```text
dadi-translator-streamlit/
├── app.py
├── requirements.txt
├── packages.txt
├── README.md
├── .gitignore
├── .streamlit/
│   ├── config.toml
│   └── secrets.example.toml
├── assets/
│   └── dadi-coach-logo.png
├── docs/
│   ├── DEPLOYMENT_GUIDE.md
│   ├── USER_GUIDE.md
│   ├── QUALITY_CHECKLIST.md
│   ├── PRODUCT_PLAN.md
│   └── TECHNICAL_NOTES.md
└── sample_files/
    └── sample_chinese_document.txt
```

## Local Setup

1. Install Python 3.10 or higher.
2. Open the project folder.
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run the app:

```bash
streamlit run app.py
```

5. Enter your OpenAI API key in the sidebar, or add it to `.streamlit/secrets.toml`.

## Streamlit Secrets Format

Create `.streamlit/secrets.toml` locally or add the same values in Streamlit Cloud Secrets:

```toml
OPENAI_API_KEY = "your_openai_api_key_here"
OPENAI_MODEL = "gpt-4.1-mini"
```

## Basic Use

1. Upload a Simplified Chinese document.
2. Review the extracted Chinese text.
3. Click **Translate to English**.
4. Review and edit the English translation.
5. Click **Download Word Document**.

## Output Format

The generated Word document uses:

- One-column English layout
- Centered English title
- Dadi Coach logo in the header
- Professional Calibri-style formatting
- Footer label: `Dadi Translator | Generated English Translation`
- File name based on the translated English title

## Recommended First Deployment

Use Streamlit Community Cloud because this app is Python-based and focuses on document processing, translation, preview, and DOCX generation.
