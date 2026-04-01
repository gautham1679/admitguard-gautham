# Research Notes — AdmitGuard

## Problem Understanding
The admission pipeline has 6 stages. Ineligible candidates are only caught at
stage 5 (Document Verification), costing 40+ hours per cohort.

## Root Cause
Zero validation at data entry point. Anyone can type anything into the Google
Sheet. Counselors aren't always trained on eligibility criteria.

## Key Insight: Two Types of Rules
Not all rules are equal:
- STRICT rules have zero business justification for exceptions (e.g., fake Aadhaar
  numbers, invalid emails). These must be hard blocks.
- SOFT rules have legitimate edge cases (e.g., a 36-year-old with exceptional
  profile). These need documented exceptions, not hard blocks.

## Why JSON Config?
Rules change between cohorts. If thresholds are hardcoded, every rule change
requires a developer. Moving to JSON means the ops team can update rules.json
without any code deployment.

## Why localStorage for Audit Trail?
The brief says "lightweight & deployable — no heavy infrastructure." localStorage
gives us persistence without a backend server. Trade-off: data is local to browser.
Production upgrade would be a Firebase/Supabase backend.

## Vibe Coding Observations
- One feature per prompt produced much cleaner results than asking for everything
- Providing the existing code in each prompt prevented the AI from rebuilding from scratch
- The R.I.C.E. framework made prompts significantly more precise
- Specifying exact error messages in prompts prevented vague AI-generated messages

## Tools Used
- Google AI Studio (Gemini 2.5 Pro) — code generation
- VS Code — file editing and terminal
- GitHub — version control
- Chrome DevTools — testing and debugging