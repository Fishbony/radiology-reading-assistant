# Radiology Reading Assistant

A general-purpose radiology image-interpretation prompt/skill framework for X-ray, CT, MRI, fluoroscopy, and dynamic imaging. It is designed to help clinicians and learners structure image review, describe key imaging findings, build differential diagnoses, identify urgent findings, and draft radiology-style impressions.

## Scope

This project is body-wide rather than organ-specific. It covers a structured workflow for:

- Chest imaging
- Cardiovascular and vascular imaging
- Neuroradiology and head & neck imaging
- Abdominal and gastrointestinal imaging
- Hepatobiliary, pancreatic, and splenic imaging
- Genitourinary imaging
- Female pelvis and obstetric-related imaging safety considerations
- Musculoskeletal imaging
- Spine imaging
- Pediatric imaging safety considerations
- Oncologic imaging and treatment-response assessment
- Emergency radiology
- Dynamic imaging such as fluoroscopy, defecography, and cine MRI

## What this is

- A structured radiology reasoning framework
- A differential-diagnosis support prompt
- A report-drafting aid
- A checklist for image-review completeness and safety
- Literature, textbook, and similar-case image support when references are available
- Feedback-based self-iteration: when a diagnosis is corrected, the framework records de-identified lessons and updates future reasoning
- A reusable AI skill/prompt for radiology education and workflow assistance

## What this is not

This project is not a medical device, not a diagnostic product, and not a substitute for a qualified radiologist or other licensed clinician. It does not provide definitive diagnoses. Final interpretation requires complete imaging data, clinical history, laboratory data, prior studies, and professional judgment.

See `references/safety-disclaimer.md`.

## Recommended answer format

```text
1. Image/data adequacy
2. Key imaging findings
3. Most likely diagnosis, with confidence
4. Differential diagnosis
5. Urgent/critical findings to exclude
6. Recommended additional imaging or clinical correlation
7. Suggested report wording
```

## Repository structure

```text
SKILL.md                                  Main reusable skill/prompt
README.md                                 Project overview
references/safety-disclaimer.md           Medical safety disclaimer
references/body-wide-checklist.md         Body-wide interpretation checklist
templates/structured-reading-template.md  General output template
templates/report-template.md              Report-style template
templates/differential-diagnosis-template.md Differential diagnosis template
examples/example-general-case.md          Example usage
```

## License

Suggested license: CC BY-NC 4.0 if you want to prevent direct commercial reuse, or MIT if you want maximum adoption. Choose one before publishing.
