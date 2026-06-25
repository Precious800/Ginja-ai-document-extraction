# Healthcare Claim Extraction Pipeline

## Overview
A document extraction pipeline for healthcare claims supporting PDF and image files. Built for the Ginja AI AI/ML Engineering Intern case study.

It processes healthcare documents (PDFs and images) and extracts structured claim information using a hybrid AI approach combining:

- PDF text extraction
- OCR (EasyOCR + OpenCV preprocessing)
- Vision Language Model (Groq API)

The system outputs structured JSON records with confidence scoring and validation checks.

## Features
- Automatic detection of text-based vs scanned PDFs
- PDF text extraction with table support (pdfplumber + PyMuPDF)
- OCR for scanned documents (EasyOCR + OpenCV)
- Vision Language Model (VLM) extraction via Groq API
- Field parsing, normalization, and validation
- JSON output with confidence scores
- Batch processing support
- Progress tracking during execution

## Extracted Fields
The pipeline extracts the following fields:

- claim_id
- member_id
- provider_name
- provider_id
- date_of_service
- diagnosis_code
- procedure_code
- claimed_amount
- currency
- invoice_number

## Pipeline Workflow

Input Document
→ Format Detection (PDF / Image / Scanned PDF)
→ PDF Text Extraction OR OCR OR VLM
→ Field Extraction (Regex)
→ Normalization
→ Validation
→ Confidence Scoring
→ Structured JSON Output

## How to Run

### 1. Install Dependencies
```bash
pip install pdfplumber PyMuPDF opencv-python easyocr numpy groq pillow
