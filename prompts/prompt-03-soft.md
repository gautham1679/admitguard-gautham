# Prompt 03 — Soft Validation Rules

## R.I.C.E. Framework

**Role:** You are a senior frontend developer adding a second tier of validation
to a compliance form. This tier shows warnings (not hard blocks) for borderline
eligibility criteria.

**Intent:** Add soft (warning) validation to the AdmitGuard form. Unlike strict
rules, soft rule violations do NOT block submission immediately. Instead, they
show a yellow/orange warning banner below the field, and they will later trigger
an exception handling flow (which we will add in the next prompt). For now, just
show the warning message clearly.

**Constraints:**
- Warning messages use amber/orange color (#f39c12), NOT red
- Warning icon: use ⚠️ emoji before the message
- Warning appears inline below the field
- Soft rule violations do NOT disable the submit button (yet — exception system comes next)
- Keep all existing strict validation intact
- Single HTML file

**Soft Rules to implement:**

1. **Age:**
   - Valid range: 18 to 35 years (inclusive)
   - Below 18: ⚠️ "Candidate is under 18. Exception required."
   - Above 35: ⚠️ "Candidate is above 35. Exception required."

2. **Graduation Year:**
   - Valid range: 2015 to 2025 (inclusive)
   - Outside range: ⚠️ "Graduation year must be between 2015 and 2025. Exception required."

3. **Percentage / CGPA:**
   - If value > 10: treated as percentage — must be ≥ 60
   - If value ≤ 10: treated as CGPA — must be ≥ 6.0
   - Below threshold: ⚠️ "Percentage below 60% (or CGPA below 6.0). Exception required."

4. **Screening Test Score:**
   - Valid range: 0 to 100
   - Must be ≥ 40
   - Below 40: ⚠️ "Screening score below minimum (40/100). Exception required."

**Examples:**
- Age 17: shows amber warning ⚠️ (does NOT block submit by itself)
- Age 25: no warning ✓
- Percentage 55: shows amber warning ⚠️
- Percentage 75: no warning ✓
- CGPA 5.5 (entered as 5.5): shows amber warning ⚠️
- Score 39: shows amber warning ⚠️
- Score 65: no warning ✓

**Output:** Complete updated index.html. No placeholders.