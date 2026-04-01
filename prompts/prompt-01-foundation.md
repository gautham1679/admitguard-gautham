# Prompt 01 — Foundation Form

## R.I.C.E. Framework

**Role:** You are a senior frontend developer building an internal business tool
for an education company's admissions operations team.

**Intent:** Create a single-page HTML admission form called "AdmitGuard" with
exactly 11 fields and a clean card-based layout. This form will be used by
counselors to enter candidate data. Do NOT add any validation logic yet —
just build the structure and layout.

**Constraints:**
- Single HTML file only (no separate CSS or JS files)
- No external frameworks or libraries (no Bootstrap, no jQuery)
- Card layout with white background, subtle shadow, 16px padding
- Use a professional color scheme: dark navy header (#1a1a2e), orange accent (#e67e22)
- All fields must have clear labels above them
- Form must have a "Submit Candidate" button at the bottom (disabled for now)
- Mobile-friendly layout

**The 11 fields (in this exact order):**
1. Full Name (text input)
2. Email Address (email input)
3. Phone Number (tel input, placeholder: 10-digit mobile number)
4. Qualification (dropdown with options: Select Qualification, B.Tech, B.E., MCA, M.Tech, MBA, BCA, B.Sc, Other)
5. Interview Status (dropdown with options: Select Status, Cleared, Rejected, Pending)
6. Aadhaar Number (text input, placeholder: 12-digit Aadhaar)
7. Offer Letter Issued (dropdown: Select, Yes, No)
8. Age (number input, placeholder: Candidate age in years)
9. Graduation Year (number input, placeholder: e.g. 2022)
10. Percentage / CGPA (number input, placeholder: e.g. 75 or 8.5)
11. Screening Test Score (number input, placeholder: Score out of 100)

**Examples:**
- Good layout: Each field has a label on top, input below, with 8px gap between label and input
- Good button: Full-width, orange background, white text, rounded corners
- Bad: Don't use a table layout. Don't use inline styles for everything.

**Output:** A single complete index.html file. No placeholders, no "add your CSS here" comments.