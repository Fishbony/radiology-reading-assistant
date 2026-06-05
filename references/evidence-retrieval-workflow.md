# Evidence Retrieval and Similar-Case Workflow

Use this workflow when a radiology interpretation should be supported by literature, textbook-style references, or visually similar published/open cases.

## 1. Build the search query from the image

Extract:
- Modality: X-ray, CT, MRI, fluoroscopy, ultrasound, cine/video
- Body region and organ
- Key pattern: mass, wall thickening, ring enhancement, ground glass, lytic lesion, diffusion restriction, hemorrhage, calcification, fat, gas, obstruction, etc.
- Suspected diagnosis and top differential diagnoses
- Phase/sequence: arterial, portal venous, delayed, T1, T2, DWI/ADC, FLAIR, SWI/GRE, MRCP, CTA, etc.

## 2. Search order

1. Guidelines/reporting systems: ACR, RSNA, ESR/ESGAR/ESUR, LI-RADS, PI-RADS, BI-RADS, Bosniak, RECIST, Lugano, Fleischner when applicable
2. Reviews and educational sources: RadioGraphics, Radiology, AJR, European Radiology, Insights into Imaging, organ-specific radiology journals
3. PubMed for original studies and case series
4. Open teaching files or case libraries for visually similar cases
5. Single case reports when the presentation is rare or visually close

## 3. Suggested search patterns

```text
<disease> <modality> imaging findings radiology review
<organ> <key sign> <disease> CT MRI differential diagnosis
<disease> Radiographics imaging findings
<disease> AJR CT MRI differential diagnosis
site:pubmed.ncbi.nlm.nih.gov <disease> imaging CT MRI
site:radiopaedia.org <disease> CT MRI case
```

## 4. Similar-case comparison

For each candidate source, document:

- Citation: title, source, year, DOI/PMID/URL
- Evidence type: guideline / textbook / review / case series / case report / teaching file
- Similarities: modality, location, morphology, signal/density, enhancement, distribution, complications
- Differences: sequence/phase, disease extent, patient context, treatment status, atypical features
- Whether the source image is openly licensed or only linkable

## 5. Citation wording

Good:
"This resembles the case image in [source] because both show [...]. The submitted case differs by [...], so the match is supportive but not definitive."

Avoid:
"This is definitely the same disease because it looks like an online case."

## 6. Copyright rule

Do not copy or redistribute copyrighted figures unless the license permits it. Link to the source and describe the visual similarity.
