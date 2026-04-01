# Prompt 05 — Configurable Rules Engine

## R.I.C.E. Framework

**Role:** You are a senior frontend developer refactoring a validation system
to be data-driven. The goal is to make rule thresholds configurable without
code changes.

**Intent:** Refactor the AdmitGuard index.html so that ALL validation thresholds
and rule values are read from an external config/rules.json file instead of
being hardcoded in the JavaScript. The app should fetch rules.json on page load
and use those values throughout. All existing functionality must continue to work
exactly as before.

**Constraints:**
- Use fetch() to load rules.json when the page loads
- Show a loading spinner or "Loading rules..." text while fetching
- If rules.json fails to load, show an error: "Failed to load validation rules.
  Please refresh."
- All validation logic must reference the loaded config object, not hardcoded values
- The rules.json file path is: ../config/rules.json (relative to src/index.html)
- Single HTML file for index.html, separate rules.json in config/ folder

**What gets moved to config:**
- Name: minLength
- Phone: exactDigits, mustStartWith array
- Aadhaar: exactDigits
- Age: min, max
- Graduation Year: min, max
- Percentage: minPercentage, minCGPA, cgpaThreshold
- Screening Score: min, max
- Exception: minRationaleLength, requiredKeywords array, maxExceptionsBeforeFlag

**Examples:**
- If rules.json has age.min: 18, the form validates age ≥ 18
- If someone changes age.min to 21 in the JSON file and refreshes — validation
  automatically updates to age ≥ 21 with zero code changes
- This is the entire point: ops team edits JSON, developers don't need to be involved

**Output:** Complete updated index.html that reads from rules.json.
No placeholders. Assume rules.json exists at ../config/rules.json.