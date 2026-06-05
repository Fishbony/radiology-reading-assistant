# Radiology Reading Assistant

A body-wide radiology image-interpretation prompt/skill framework for X-ray, CT, MRI, fluoroscopy, dynamic imaging, and selected ultrasound screenshots/videos.

It is designed to help clinicians, trainees, and AI assistants produce structured radiology reasoning: image adequacy assessment, urgent finding screening, systematic description, differential diagnosis, literature-supported interpretation, similar-case comparison, and report-style wording.

> Safety: this repository is for education and workflow support only. It is not a medical device and does not replace interpretation by qualified clinicians using complete original imaging data.

## Key features

- Body-wide coverage: chest, cardiovascular, neuro, head & neck, abdomen, hepatobiliary/pancreas, genitourinary, female pelvis, musculoskeletal, spine, pediatric, oncology, emergency, and dynamic imaging
- Modality-aware workflow for X-ray, CT, MRI, fluoroscopy, cine/video, and screen-recorded image stacks
- Critical-findings-first approach for emergency radiology
- Structured differential diagnosis with supporting and opposing features
- Evidence support using guidelines, textbooks, reviews, PubMed-indexed literature, and open teaching-file cases when available
- Similar-case image retrieval workflow: compare the submitted case with visually similar published or open educational images, without redistributing copyrighted images
- Feedback-based self-iteration: when a diagnosis is corrected, record de-identified lessons and update future reasoning
- Privacy-first design: do not commit DICOM files, patient images, or protected health information

## Recommended output format

```text
Image/data adequacy:
- Modality/region/sequence:
- Completeness and limitations:

Critical findings:
- Present / absent / indeterminate:

Key imaging findings:
1.
2.
3.

Most likely diagnosis:
- Diagnosis:
- Confidence:
- Rationale:

Differential diagnosis:
1. Diagnosis — supporting features; features against
2. Diagnosis — supporting features; features against

Evidence support:
- Guideline/textbook/review/case source:
- DOI/PMID/URL if available:
- Why it supports the diagnosis:

Similar-case image comparison:
- Source link if available:
- Similarities:
- Differences:
- Copyright/license note:

Recommended next step:
-

Suggested report wording:
-
```

## Repository structure

```text
SKILL.md                                      Main reusable prompt/skill
README.md                                     Project overview
LICENSE                                       CC BY-NC 4.0 summary and link
CONTRIBUTING.md                               Contribution and case-submission rules
CHANGELOG.md                                  Version history
references/safety-disclaimer.md               Medical safety disclaimer
references/body-wide-checklist.md             Body-wide interpretation checklist
references/evidence-retrieval-workflow.md     Literature and similar-case search workflow
references/feedback-learning-policy.md        De-identified correction-learning policy
templates/structured-reading-template.md      General output template
templates/report-template.md                  Report-style template
templates/differential-diagnosis-template.md  Differential diagnosis template
templates/literature-support-template.md      Evidence and similar-case template
templates/correction-learning-template.md     Feedback learning template
examples/example-general-case.md              Example usage
```

## How to use

1. Copy `SKILL.md` into your AI assistant's system prompt, skill directory, or reusable instruction library.
2. When providing images, remove patient identifiers and avoid uploading original clinical data unless permitted by law and institutional policy.
3. Provide minimal context when possible: age range, sex if relevant, symptoms, modality, contrast phase/sequence, prior cancer/surgery, and the clinical question.
4. Ask for one of the output styles:
   - concise clinical interpretation
   - teaching explanation
   - differential diagnosis only
   - report wording
   - evidence-supported answer with similar-case references
5. If the answer is corrected by pathology, surgery, follow-up, or expert consensus, use `templates/correction-learning-template.md` to record a de-identified lesson.

## Evidence philosophy

The framework should prefer established, high-quality sources:

1. Official reporting systems, society guidelines, and consensus statements
2. Major radiology textbooks and educational references
3. High-quality radiology reviews such as RadioGraphics, Radiology, AJR, European Radiology, Insights into Imaging, Abdominal Radiology, Neuroradiology, Skeletal Radiology
4. Multicenter studies and case series
5. Single case reports or open teaching-file cases when visually very similar

The assistant should not claim to have read all books or all papers. It should describe the best available evidence it can retrieve or cite.

## Privacy and patient data

Do not commit or publish:

- DICOM files
- screenshots with patient identifiers
- accession numbers
- exact dates of service
- face photographs or uniquely identifying anatomy without proper consent/de-identification
- local hospital or operator-specific private information

The `.gitignore` blocks common medical image formats and media files by default.

## License

This repository is released under CC BY-NC 4.0. See `LICENSE`.

You may share and adapt the material with attribution for non-commercial purposes. Commercial use is not permitted under this license.
