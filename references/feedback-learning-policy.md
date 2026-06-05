# Feedback Learning Policy

This project supports de-identified learning from corrected interpretations.

## What can be stored

- Initial impression
- Final diagnosis
- Evidence source category: pathology, surgery, follow-up, expert report, user feedback, literature
- De-identified imaging clue that was missed or underweighted
- Mimic/pitfall
- A reusable rule for future cases
- Suggested reference to add

## What must not be stored

- Patient name or initials
- Medical record number, accession number, phone number, address, or exact date of service
- Original DICOM or identifiable screenshots
- Face images or uniquely identifying anatomy without permission
- Institution-specific private workflow details

## When to update the skill

Update `SKILL.md` or a reference note when the correction reveals a broadly useful rule, for example:

- A common mimic was omitted from the differential.
- A critical finding was not prioritized.
- A disease has a known atypical presentation that the framework did not mention.
- A better evidence source or reporting guideline should be cited.

## De-identified learning entry

```text
Learning entry:
- Pattern:
- Initial impression:
- Final diagnosis:
- Key discriminating feature:
- Pitfall:
- Future rule:
- Evidence source type:
```
