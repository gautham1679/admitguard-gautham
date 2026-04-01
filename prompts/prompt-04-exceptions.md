# Prompt 04 — Exception Handling System

## R.I.C.E. Framework

**Role:** You are a senior frontend developer building a compliance override
system for a regulated admissions process. Every exception must be formally
justified and documented.

**Intent:** When any soft rule is violated (Age, Graduation Year, Percentage,
Screening Score), show a "Request Exception" toggle button below the warning.
If the operator clicks it, show a rationale text area. The rationale must pass
validation before the form can be submitted. Track how many exceptions are
being requested, and flag the submission if more than 2 exceptions are used.

**Constraints:**
- "Request Exception" appears ONLY when a soft rule warning is showing
- The rationale text area appears only after the operator clicks "Request Exception"
- The submit button remains disabled until EITHER: no soft rule is violated, OR
  all violated soft rules have valid rationale entered
- Keep all existing strict and soft validation intact
- Single HTML file

**Exception Validation Rules:**

For EACH soft rule violation where "Request Exception" is toggled ON:
1. A text area appears with label: "Exception Rationale (required)"
2. Rationale must be at minimum 30 characters
   - Live character counter shown: "X / 30 characters minimum"
   - Counter turns green when ≥ 30 chars
3. Rationale must contain at least ONE of these exact phrases (case-insensitive):
   - "approved by"
   - "special case"
   - "documentation pending"
   - "waiver granted"
4. If neither condition is met, show: "Rationale must be ≥30 chars and contain:
   'approved by', 'special case', 'documentation pending', or 'waiver granted'"

**Manager Review Flag:**
- Count how many soft rules have "Request Exception" toggled ON
- If count > 2, show a prominent red banner at the top of the form:
  "⚠️ FLAGGED FOR MANAGER REVIEW: This submission has 3+ exceptions and requires
  manager approval before processing."
- This banner does NOT block submission — it just marks it

**Submit Button Logic:**
The submit button is enabled ONLY when:
- All strict rules pass (no red errors)
- AND for every soft rule violation: "Request Exception" is toggled ON AND
  the rationale is valid (≥30 chars + required keyword)
- Interview status is not "Rejected"

**Examples:**
- Age 17, no exception toggled → submit blocked
- Age 17, exception toggled, rationale: "approved by senior manager for special intake" → submit enabled ✓
- Age 17, exception toggled, rationale: "ok" → submit blocked (too short, no keyword)
- 3 soft violations, all with valid exceptions → form shows manager flag banner, submit enabled

**Output:** Complete updated index.html. No placeholders.