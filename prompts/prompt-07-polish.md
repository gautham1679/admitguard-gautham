# Prompt 07 — UI Polish and Edge Cases

## R.I.C.E. Framework

**Role:** You are a senior frontend developer doing final QA and polish on a
business compliance tool before it goes to stakeholder review.

**Intent:** Fix edge cases, improve UX clarity, and ensure the app looks and
feels professional for a business presentation.

**Constraints:** Single HTML file. No external libraries.

**Polish Items:**

1. **Success State:** After successful submission, show a green success card:
   "✅ Candidate Submitted Successfully"
   Show: Candidate name, timestamp, number of exceptions used, flagged status
   Include a "Submit Another Candidate" button that resets the form

2. **Form Reset:** "Submit Another Candidate" clears ALL fields, removes all
   errors and warnings, resets exception toggles

3. **Progress Indicator:** Add a simple progress bar or step indicator at the
   top showing form completion percentage (how many required fields are filled)

4. **Field Labels Enhancement:** Add a red asterisk * after labels for all
   required fields. Add "(Optional)" text for any non-required fields.

5. **Percentage/CGPA Helper:** Next to the Percentage/CGPA field, add a small
   note: "Enter % (e.g. 75) or CGPA (e.g. 7.5). Values ≤ 10 treated as CGPA."

6. **Interview Status → Offer Letter dependency:** When Interview Status changes
   to anything other than "Cleared", automatically reset Offer Letter to "No"
   and show a note: "Offer letter automatically set to No (interview not cleared)"

7. **Character counter on name field:** Show "X characters" below the name
   field as user types.

8. **Audit Log Enhancement:** Add a "View Details" button per row that shows
   a modal/popup with the complete submission record including full rationale text.

**Output:** Complete updated index.html. No placeholders.