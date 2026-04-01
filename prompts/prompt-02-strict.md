# Prompt 02 — Strict Validation Rules

## R.I.C.E. Framework

**Role:** You are a senior frontend developer adding real-time validation to
an existing admission form. You are building an internal compliance tool where
data quality is critical.

**Intent:** Add strict (hard) validation rules to the AdmitGuard form. These
rules must block form submission completely if violated. Show inline red error
messages directly below each field as the user types or when they leave the
field (on blur). The Submit button must remain disabled until ALL strict rules
pass.

**Constraints:**
- Validation triggers on input AND on blur (when user clicks away from field)
- Error messages appear in red (#e74c3c) directly below the field
- Error text size: 12px, italic
- The Submit button stays grey and disabled until all strict errors are cleared
- Do not remove any existing HTML structure or styling
- Keep everything in a single HTML file

**Strict Rules to implement (ZERO TOLERANCE — no overrides):**

1. **Full Name:**
   - Minimum 2 characters
   - Must not contain any numbers (0-9)
   - Error: "Name must be at least 2 characters and contain no numbers"

2. **Email Address:**
   - Must match valid email format (contains @, has domain, has extension)
   - Error: "Please enter a valid email address"

3. **Phone Number:**
   - Must be exactly 10 digits
   - Must start with 6, 7, 8, or 9
   - No spaces, no dashes, numbers only
   - Error: "Phone must be 10 digits starting with 6, 7, 8, or 9"

4. **Qualification:**
   - Must not be "Select Qualification" (must make a real selection)
   - Error: "Please select a qualification"

5. **Interview Status:**
   - If "Rejected" is selected, show a prominent red banner: "This candidate
     has been rejected in the interview. Submission is blocked."
   - Submit button must be disabled and cannot be re-enabled while Rejected is selected
   - Error: "Submission blocked: Interview status is Rejected"

6. **Aadhaar Number:**
   - Must be exactly 12 digits
   - Numbers only, no spaces or dashes
   - Error: "Aadhaar must be exactly 12 digits"

7. **Offer Letter Issued:**
   - Must not be "Select" (must make a real selection)
   - Additionally: if Interview Status is NOT "Cleared", then "Offer Letter Issued: Yes"
     must be blocked with error: "Offer letter can only be issued if interview is Cleared"
   - Error: "Please select an offer letter status"

**Examples:**
- Valid phone: 9876543210 ✓
- Invalid phone: 1234567890 ✗ (doesn't start with 6-9)
- Invalid phone: 98765432 ✗ (only 8 digits)
- Valid Aadhaar: 234567891234 ✓
- Invalid Aadhaar: 12345 ✗ (too short)
- Valid name: "Rahul Singh" ✓
- Invalid name: "R2D2" ✗ (contains numbers)

**Output:** The complete updated index.html file with all strict validation added.
No placeholders. Complete working code only.