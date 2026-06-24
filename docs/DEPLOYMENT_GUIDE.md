# Dadi Translator - Streamlit Cloud Deployment Guide

## Recommended deployment settings

Use Streamlit Community Cloud, not Vercel.

When creating the app:

- Repository: your GitHub repository
- Branch: main
- Main file path: `app.py`
- Python version: `3.11`

Important: If the app was already created using another Python version, delete the failed app and deploy again. Streamlit Community Cloud lets you choose Python version in Advanced settings during deployment.

## Required repository root files

The GitHub repository root should directly contain:

```text
app.py
requirements.txt
runtime.txt
README.md
assets/
docs/
sample_files/
.streamlit/
```

Do not place these files inside an extra folder.

## Secrets

In Streamlit Cloud, open app settings and add:

```toml
OPENAI_API_KEY = "your_openai_api_key_here"
OPENAI_MODEL = "gpt-4.1-mini"
```

## Cloud-safe file support

This stable version supports:

- `.docx`
- `.txt`
- `.md`

For old `.doc` files, open the file in Microsoft Word or WPS and save it as `.docx` first.

## If requirements installation fails

Use the simplified `requirements.txt` included in this repository:

```text
streamlit
openai
python-docx
mammoth
markdown
beautifulsoup4
```

This version removes heavy or external dependencies that commonly cause cloud installation failures.
