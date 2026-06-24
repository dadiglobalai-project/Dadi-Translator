# Technical Notes: Dadi Translator Streamlit Version

## Technology Stack

- Python
- Streamlit
- OpenAI API
- Mammoth for DOCX extraction
- Python-docx for Word document generation
- Markdown and BeautifulSoup for Markdown text extraction
- Antiword for legacy DOC extraction

## Application Flow

```text
User Upload
    ↓
File Type Detection
    ↓
Text Extraction
    ↓
Title Detection
    ↓
AI Translation
    ↓
Editable Preview
    ↓
DOCX Generation
    ↓
Download
```

## File Extraction Logic

### DOCX

Uses Mammoth to extract raw text from Word documents.

### TXT

Reads the uploaded file using common encodings such as UTF-8, GB18030, Big5, and Latin-1.

### MD

Converts Markdown into HTML and extracts readable text.

### DOC

Uses antiword if available. If extraction fails, the user should convert the file to DOCX.

## Translation Logic

The app divides the source text into chunks. Each chunk is translated separately while preserving:

- Meaning
- Section order
- Numbering
- Bullet points
- Paragraph breaks
- Professional business tone

## Word Export Logic

The generated Word document includes:

- Header with Dadi Coach logo
- Centered English title
- Subtitle
- One-column English translation
- Footer label

## Security Notes

- Do not store the OpenAI API key in GitHub.
- Use Streamlit Secrets for deployment.
- Review translated documents before external distribution.
- Do not upload confidential documents unless the company has approved the API and hosting setup.

## Limitations

- Scanned image files are not supported in the first version.
- OCR is not included.
- Extremely long documents may take longer to translate.
- Legacy DOC extraction depends on the quality and compatibility of the DOC file.
