# AdmitGuard — Admission Data Validation & Compliance System

## What This Is
A form-based admission data entry system that replaces unstructured spreadsheets.
Built to enforce eligibility rules at the point of data entry, preventing ineligible
candidates from advancing through the admission pipeline.

## The Problem It Solves
Ineligible candidates were only being caught at Document Verification (stage 5),
after 40+ hours of company time had already been wasted per cohort.

## Features
- Real-time strict validation (Name, Email, Phone, Aadhaar, Interview, Qualification, Offer Letter)
- Soft rule validation with exception handling (Age, Graduation Year, Percentage, Screening Test)
- Configurable rules via config/rules.json — no code changes needed
- Audit trail of all submissions with timestamps and exception logs
- Manager review flag when >2 exceptions are used in one submission

## How to Run
Open `src/index.html` in any web browser. No installation required.

## Built With
- Google AI Studio (Gemini) for AI-assisted development
- Vanilla HTML, CSS, JavaScript (no frameworks)

## Project By
Gautham krishna