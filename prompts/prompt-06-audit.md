# Prompt 06 — Audit Trail System

## R.I.C.E. Framework

**Role:** You are a senior frontend developer building a compliance audit system.
Every data submission must be permanently logged for accountability.

**Intent:** Add an audit trail to AdmitGuard. When the form is submitted
successfully, save a complete record to localStorage. Add a separate "Audit Log"
view (accessible via a button) that displays all past submissions in a table.

**Constraints:**
- Use localStorage to persist submissions across page refreshes
- The audit log view replaces the form view (toggle between them with a button)
- Single HTML file
- Audit log table must be sortable by timestamp (newest first by default)

**What to log for each submission:**
```json
{
  "id": "auto-generated UUID or timestamp-based ID",
  "timestamp": "ISO 8601 format e.g. 2025-04-02T14:30:00",
  "submittedBy": "operator (use 'Counselor' as default for now)",
  "candidateData": {
    "name": "",
    "email": "",
    "phone": "",
    "qualification": "",
    "interviewStatus": "",
    "aadhaar": "XXXX-XXXX-XXXX (masked — show only last 4 digits)",
    "offerLetter": "",
    "age": "",
    "graduationYear": "",
    "percentageOrCGPA": "",
    "screeningScore": ""
  },
  "exceptionsUsed": [
    {
      "field": "age",
      "rationale": "full rationale text"
    }
  ],
  "exceptionCount": 0,
  "flaggedForReview": false,
  "status": "Submitted"
}
```

**Audit Log UI:**
- Header: "AdmitGuard — Submission Audit Log"
- A table with columns: Timestamp | Candidate Name | Email | Exceptions | Flagged | Status
- Flagged submissions highlighted in red background row
- A "Clear All Logs" button (with confirmation dialog)
- A "← Back to Form" button
- A "Export as JSON" button that downloads all logs as a .json file
- Show "No submissions yet" if log is empty

**Email Uniqueness Check:**
- When validating email in the form, check against all emails stored in localStorage
- If email already exists in audit log: show strict error "This email has already
  been submitted. Duplicate entries are not allowed."

**Examples:**
- Submit form → success message → entry appears in audit log
- Submit same email again → blocked with "Duplicate email" error
- Flagged submission → shows red row in audit table

**Output:** Complete updated index.html. No placeholders.