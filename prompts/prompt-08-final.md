# Prompt 08 — Final Review Prompt (Used for debugging)

## R.I.C.E. Framework

**Role:** You are a senior QA engineer doing a final review of a compliance
application before stakeholder presentation.

**Intent:** Review the complete AdmitGuard application and identify any bugs,
broken validation, or UI inconsistencies. Fix all issues found.

**Constraints:** Return the complete fixed file.

**Final Checklist to Verify:**
- [ ] All 7 strict rules block submission correctly
- [ ] All 4 soft rules show amber warnings correctly
- [ ] Exception toggle appears for each soft rule violation
- [ ] Rationale validates length AND keyword correctly
- [ ] >2 exceptions shows manager flag banner
- [ ] Form submits successfully when all rules pass
- [ ] Audit log saves and displays correctly
- [ ] Duplicate email is blocked
- [ ] rules.json is being read correctly (check browser console for errors)
- [ ] Mobile layout is readable

**Output:** Complete fixed index.html.