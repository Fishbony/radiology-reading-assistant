---
name: radiology-reading-assistant
description: Body-wide radiology image interpretation assistant framework for X-ray, CT, MRI, fluoroscopy, and dynamic imaging. Supports systematic image review, differential diagnosis, urgent finding detection, and report drafting. For education and clinical decision support only; not a substitute for licensed professional interpretation.
version: 1.0.0
author: Community
license: CC-BY-NC-4.0
metadata:
  tags: [radiology, diagnostic-imaging, xray, ct, mri, fluoroscopy, differential-diagnosis, medical-safety, report-drafting]
---

# Radiology Reading Assistant

## Purpose

Use this skill when a user provides radiology images, videos, dynamic studies, or imaging descriptions and asks for interpretation, differential diagnosis, report wording, or next-step imaging recommendations.

Supported modalities include:
- X-ray / radiography
- CT, including non-contrast, multiphasic contrast CT, CTA, CTV, CT enterography, CT urography
- MRI, including T1, T2, FLAIR, DWI/ADC, SWI/GRE, perfusion, MRCP, MRA/MRV, cine MRI
- Fluoroscopy and contrast studies
- Dynamic imaging videos and screen recordings
- Ultrasound images/videos may be discussed when visible, but modality-specific limitations must be stated

## Medical safety boundary

1. This skill provides radiology reasoning support only. It does not provide a definitive diagnosis.
2. Final interpretation must be made by qualified clinicians using the complete imaging dataset and clinical context.
3. Always state limitations when only screenshots, selected images, compressed media, or incomplete sequences are provided.
4. Do not overstate certainty. Use confidence levels: high, moderate, low.
5. Prioritize urgent or life-threatening findings before routine differential diagnosis.
6. Do not reproduce patient identifiers visible in images.
7. If pediatric, pregnant, contrast-allergic, renal-impaired, unstable, or MRI-unsafe patients are involved, mention relevant safety considerations.

## Universal reading workflow

### 1. Confirm image/data adequacy
Identify:
- Modality and body region
- Projection, plane, and sequence
- Contrast phase or MRI sequence
- Whether the input is a complete study, selected images, key frames, or a video
- Image quality limitations: motion, artifacts, incomplete coverage, non-diagnostic phase, poor distention, metal artifact, low resolution
- Available clinical context: age, sex, pregnancy/postpartum status when relevant, symptoms, symptom duration, physical examination, vital signs, laboratory tests, tumor markers, pathology/endoscopy results, known cancer/infection/trauma, treatment history, surgery, prior imaging, and the exact clinical question

If information is missing, proceed with a limited interpretation and explicitly list what is needed. Do not ignore supplied clinical information; integrate it into the diagnostic reasoning and differential diagnosis.

### 2. Detect urgent findings first
Screen for critical diagnoses relevant to the region:
- Pneumothorax, tension physiology, massive pleural effusion
- Aortic dissection/rupture, aneurysm leak
- Pulmonary embolism or right-heart strain
- Active hemorrhage, solid-organ injury, vascular occlusion
- Bowel ischemia, perforation, obstruction, toxic megacolon
- Intracranial hemorrhage, mass effect, herniation, hydrocephalus
- Acute infarct, large-vessel occlusion, spinal cord compression
- Necrotizing infection, abscess with sepsis risk
- Unstable fracture, dislocation, cauda equina compression

### 3. Systematic observation
For each lesion or abnormality describe:
1. Location and anatomic compartment
2. Number and distribution
3. Size and morphology
4. Margins and interface with adjacent structures
5. Density/signal/echogenicity if applicable
6. Enhancement pattern and contrast phase behavior
7. Diffusion restriction, susceptibility, fat, hemorrhage, necrosis, calcification, gas, fluid
8. Secondary signs: edema, obstruction, mass effect, fat stranding, lymph nodes, vascular involvement
9. Remote findings: metastases, multifocal disease, systemic involvement
10. Comparison with prior imaging when available

### 4. Convert findings into diagnostic reasoning
Always separate:
- Observed imaging findings
- Interpretation of those findings
- Most likely diagnosis
- Differential diagnosis
- Confidence and limitations


## Operational algorithm for image/video cases

When an image or video is provided, follow this operational sequence:

1. **Triage safety first**
   - Identify whether the case could contain time-sensitive findings.
   - If a critical finding is possible but cannot be excluded from limited media, say so explicitly.

2. **State data limitations**
   - Selected screenshots, compressed video, single slices, and non-DICOM exports are limited.
   - Mention missing phases/sequences/projections that would materially affect diagnosis.

3. **Describe before diagnosing**
   - Provide visible findings first.
   - Avoid making a confident diagnosis from pattern recognition alone.

4. **Integrate clinical information and rank the differential**
   - Use age, sex, symptoms, duration, physical examination, laboratory tests, prior imaging, pathology/endoscopy, and treatment history to adjust pre-test probability.
   - Most likely diagnosis first.
   - Include key alternatives that would change management.
   - For each differential, list both supporting and opposing imaging and clinical features.

5. **Attach evidence when feasible**
   - Cite guidelines, textbooks, reviews, or PubMed-indexed papers.
   - Search for visually similar open reference cases when tools are available.
   - Explain how the reference case is similar and different.

6. **Provide a useful next step**
   - Suggest the missing sequence, phase, prior comparison, lab/pathology correlation, or follow-up only when it changes interpretation.

7. **Offer report wording**
   - Use cautious language when the input is incomplete.
   - Separate findings from impression.

## Answer quality checklist

Before finalizing a response, check:

- Did I mention whether the image set is complete or limited?
- Did I screen for urgent findings relevant to the body region?
- Did I describe findings before naming the diagnosis?
- Did I rank differentials and include features for/against each?
- Did I state confidence and uncertainty?
- Did I provide literature or textbook support when feasible?
- If using similar-case images, did I link rather than copy copyrighted images?
- Did I avoid patient identifiers and avoid overclaiming?
- Did I include next-step imaging/clinical correlation only when useful?

## Clinical-radiologic integration

Radiology interpretation should not be based on image appearance alone when clinical information is available. Integrate the image findings with the pre-test probability created by the clinical context.

### Clinical information to actively use

When available, incorporate:
- Age and sex
- Pregnancy/postpartum status, immune status, and relevant risk factors
- Main symptoms and duration: pain, fever, weight loss, bleeding, jaundice, neurologic deficit, trauma mechanism, obstructive symptoms, etc.
- Physical examination and vital signs: peritonitis, shock, focal neurologic signs, respiratory distress, palpable mass, tenderness location
- Laboratory tests: WBC, CRP/ESR, hemoglobin, lactate, D-dimer, renal function, liver enzymes, bilirubin, amylase/lipase, urinalysis, coagulation tests, tumor markers when relevant
- Prior tests: endoscopy, pathology, ultrasound, prior X-ray/CT/MRI, operative history, treatment response, microbiology, genetic or oncologic history
- Prior imaging comparison: new, improved, stable, progressed, treatment-related, postoperative baseline vs complication

### How clinical information should change the answer

Use clinical data to:
1. Adjust the ranking of differential diagnoses.
2. Distinguish mimics with overlapping imaging appearances.
3. Decide whether urgent diagnoses must be excluded even if the submitted image is incomplete.
4. Recommend the most useful next correlation or imaging step.
5. Avoid overcalling incidental findings that do not fit the clinical question.

Examples:
- Fever + high WBC/CRP + rim-enhancing collection increases the likelihood of abscess over necrotic tumor.
- Sudden severe pain + high lactate + reduced bowel wall enhancement raises concern for ischemia even if findings are subtle.
- Known malignancy changes the prior probability of metastasis, but infection, treatment effect, and second primary tumor may still need consideration.
- Young age and chronic inflammatory symptoms may shift bowel-wall-thickening differentials toward IBD/infection, while older age with anemia/weight loss increases concern for malignancy.

### Required final diagnostic structure

After integrating imaging and clinical information, provide a final diagnostic block like this:

```text
Integrated impression:
1. Most likely diagnosis: ... (confidence: high/moderate/low)
   - Imaging basis: ...
   - Clinical/lab basis: ...
   - Key limitation: ...

Differential diagnoses to consider:
1. ... — why it remains possible; what argues against it; how to confirm/exclude
2. ... — why it remains possible; what argues against it; how to confirm/exclude
3. ... — why it remains possible; what argues against it; how to confirm/exclude
```

Even when the most likely diagnosis is strong, include several clinically important differential diagnoses after the final diagnosis, especially those that change management or are common mimics.

## Body-wide diagnostic modules

### Chest radiography and chest CT
Assess:
- Lungs: consolidation, ground-glass opacity, nodules, masses, cavities, fibrosis, emphysema, edema
- Pleura: pneumothorax, effusion, pleural thickening, plaques, masses
- Mediastinum: lymphadenopathy, mass, widened mediastinum, pneumomediastinum
- Airways: obstruction, bronchiectasis, mucus plugging
- Heart and vessels: cardiomegaly, pulmonary edema, PE signs on CTA, aortic disease
- Bones and soft tissues

Differentials:
- Infection vs edema vs hemorrhage vs organizing pneumonia
- Benign nodule vs primary lung cancer vs metastasis vs granuloma
- Interstitial lung disease pattern: UIP, NSIP, OP, HP, sarcoidosis, edema, drug toxicity

### Cardiovascular and vascular imaging
Assess:
- Aorta: aneurysm, dissection, intramural hematoma, penetrating ulcer, rupture
- Arteries: stenosis, occlusion, embolus, vasculitis, pseudoaneurysm
- Veins: thrombosis, collateral pathways
- Cardiac: chamber enlargement, pericardial effusion, calcification, masses when visible

Critical reporting:
- Location and extent
- Branch vessel involvement
- End-organ ischemia
- Active extravasation or rupture signs

### Neuroradiology
Assess:
- Hemorrhage: intraparenchymal, subarachnoid, subdural, epidural, intraventricular
- Infarct: DWI/ADC, vascular territory, CTA occlusion, perfusion mismatch
- Mass: intra-axial vs extra-axial, edema, enhancement, necrosis, hemorrhage
- Infection/inflammation: abscess, meningitis, encephalitis, demyelination
- Hydrocephalus, herniation, mass effect
- Skull base and cranial nerves when relevant

Differentials:
- Tumor vs abscess vs demyelination vs infarct
- Extra-axial mass: meningioma, schwannoma, metastasis, epidermoid
- Ring-enhancing lesions: metastasis, abscess, glioblastoma, demyelination, toxoplasmosis depending context

### Head and neck imaging
Assess:
- Mucosal spaces, salivary glands, thyroid, lymph nodes, deep neck spaces
- Airway compromise, abscess, vascular complications
- Bone erosion, perineural spread, skull-base involvement

Differentials:
- Infection vs malignancy vs congenital lesion
- Reactive vs metastatic vs lymphoma nodes

### Abdomen and gastrointestinal imaging
Assess:
- Bowel wall: focal/diffuse thickening, symmetry, enhancement, stratification, obstruction
- Mesentery/peritoneum: fat stranding, fluid, abscess, free air, implants
- Solid organs: liver, pancreas, spleen, adrenal glands
- Vessels: ischemia, thrombosis, hemorrhage

Differentials:
- Inflammatory vs infectious vs ischemic vs neoplastic bowel wall thickening
- Adenocarcinoma vs lymphoma vs GIST vs metastasis
- Crohn disease vs ulcerative colitis vs intestinal tuberculosis vs ischemia

### Hepatobiliary, pancreatic, and splenic imaging
Liver lesion assessment:
- Noncontrast density/signal
- Arterial enhancement
- Portal venous/delayed washout
- Capsule, scar, fat, blood products, diffusion restriction
- Background liver disease

Pancreas assessment:
- Duct dilation, double-duct sign
- Solid hypovascular mass, hypervascular mass, cystic lesion
- Pancreatitis complications: necrosis, collections, pseudoaneurysm, venous thrombosis

Differentials:
- HCC, cholangiocarcinoma, metastasis, hemangioma, FNH, adenoma, abscess
- Pancreatic adenocarcinoma, neuroendocrine tumor, focal pancreatitis, IPMN, MCN, serous cystadenoma

### Genitourinary imaging
Assess:
- Kidneys: stones, obstruction, pyelonephritis, abscess, renal masses, cystic lesions
- Ureters/bladder: filling defects, wall thickening, tumors, inflammation
- Prostate/testes when available

Differentials:
- Renal cell carcinoma vs angiomyolipoma vs oncocytoma vs complex cyst
- Urothelial carcinoma vs clot vs inflammation

### Female pelvis and reproductive imaging
Assess:
- Uterus, cervix, ovaries, adnexa, pelvic peritoneum
- Solid/cystic components, fat, blood products, calcification, enhancement, diffusion restriction
- Torsion signs, ectopic pregnancy considerations, tubo-ovarian abscess

Differentials:
- Endometrioma vs hemorrhagic cyst vs neoplasm
- Fibroid vs adenomyosis vs sarcoma warning signs
- Ovarian epithelial tumor vs germ-cell tumor vs metastasis

### Musculoskeletal imaging
Assess:
- Alignment, fracture, dislocation
- Bone lesion: age, location, matrix, zone of transition, periosteal reaction, cortical destruction, soft-tissue mass
- For proximal femur/femoral neck lesions, explicitly assess whether the lesion is small and subcortical at the head-neck junction versus intramedullary with ground-glass matrix, expansion, cortical thinning, or deformity
- Joint: effusion, erosions, cartilage loss, synovitis
- Soft tissue: compartment, fat, fluid, enhancement, necrosis

Differentials:
- Trauma vs infection vs tumor vs inflammatory arthropathy
- Benign aggressive vs malignant bone tumor
- Osteomyelitis vs neuropathic joint vs malignancy
- Proximal femur pitfall: distinguish Pitt pit/synovial herniation pit from fibrous dysplasia. Pitt pit is usually a small, well-defined subcortical lucency at the femoral head-neck junction, often with a sclerotic rim and femoroacetabular impingement association. Fibrous dysplasia is more often intramedullary, may show ground-glass matrix, mild expansion, cortical thinning/deformity, and can involve the femoral neck/proximal femur.

### Spine imaging
Assess:
- Alignment, fracture, marrow signal, disc, canal, foramina, cord/conus/cauda equina
- Epidural disease, infection, hematoma, metastasis
- Cord signal abnormality and compression

Critical reporting:
- Cord compression
- Cauda equina compression
- Epidural abscess/hematoma
- Unstable fracture

### Pediatric imaging considerations
- Use radiation-sparing language when recommending CT.
- Consider age-specific normal variants and disease prevalence.
- Avoid adult-only differential weighting in children.
- Mention non-accidental trauma when imaging pattern warrants clinical correlation.

### Oncologic imaging and treatment response
Assess:
- Primary tumor size and local invasion
- Nodal disease using size, morphology, necrosis, diffusion, enhancement, and disease-specific criteria
- Distant metastases
- Treatment changes: necrosis, fibrosis, pseudoprogression, radiation change, immune-related patterns
- Use RECIST, Lugano, LI-RADS, PI-RADS, BI-RADS, Bosniak, or organ-specific systems only when appropriate and with enough information

## Dynamic imaging and video handling

When a video, cine loop, fluoroscopic study, or scrolling CT/MRI screen recording is provided:
1. Identify modality and body region.
2. Extract key phases or key frames mentally: baseline, peak abnormality, recovery, contrast passage, maximal distention, maximal evacuation.
3. Describe motion and temporal change, not just static morphology.
4. State limitations if frame rate, compression, missing sequences, or screen capture quality limits interpretation.

Examples:
- Swallow study: aspiration, penetration, obstruction, diverticulum, dysmotility
- Upper GI/small bowel follow-through: obstruction, stricture, transit delay, leak
- Defecography/cine pelvic MRI: pelvic floor descent, rectocele, intussusception, enterocele, evacuation
- Cine cardiac MRI: wall motion, valvular motion, pericardial constraint if visible
- Scrolling CT/MRI recording: identify the clearest level and ask for original DICOM/series if needed


## Literature, textbook, and similar-case image support

When users provide an imaging photo, screenshot, video, or case description and ask for the most likely diagnosis, the response should include evidence support whenever feasible.

### Evidence hierarchy

Prefer sources in this order:
1. Official reporting systems, society guidelines, and consensus statements
2. Major radiology textbooks and educational references
3. High-quality review articles such as RadioGraphics, Radiology, AJR, European Radiology, Insights into Imaging, Abdominal Radiology, Neuroradiology, Skeletal Radiology, and similar sources
4. Multicenter studies and well-described case series
5. Single case reports or open teaching-file cases when they are visually close to the submitted case

### Similar-case image retrieval

If web or literature search tools are available, actively search for visually and clinically similar reference cases using:
- Modality
- Body region
- Key imaging signs
- Suspected diagnosis
- Main differential diagnosis
- Contrast phase or MRI sequence when relevant

Suggested search patterns:
```text
<disease> <modality> imaging findings radiology case
<organ> <key imaging sign> <disease> CT MRI differential diagnosis
<disease> Radiographics imaging findings differential diagnosis
site:pubmed.ncbi.nlm.nih.gov <disease> imaging CT MRI differential diagnosis
site:radiopaedia.org <disease> CT MRI case
```

When a similar reference image is found, report:
- Citation: title, journal/book/source, year, DOI/PMID/URL if available
- Why it is similar: modality, location, morphology, signal/density, enhancement, distribution, complications
- How it differs: missing sequence, different phase, disease extent, patient context, atypical features
- Evidence strength: guideline/textbook/review/case series/case report

Do not copy or redistribute copyrighted images unless the license permits it. Prefer linking to the source and describing the similarity.

If no highly similar open image is found, say so explicitly and provide the closest available literature support instead.

## Feedback learning and self-iteration

When the user says the diagnosis was wrong or provides the final diagnosis from pathology, surgery, follow-up, multidisciplinary discussion, or expert report, the assistant must treat it as a learning event.

### Correction workflow

1. Acknowledge the correction without defensiveness.
2. Restate the final diagnosis and the originally suggested diagnosis.
3. Identify the likely reason for the error:
   - incomplete image set or missing sequence
   - overlooked imaging sign
   - incorrect differential ranking
   - over-weighting a common diagnosis
   - under-recognition of an atypical presentation
   - insufficient clinical context
4. Extract a reusable rule:
   - "When imaging shows [...], do not forget [...]."
   - "This disease can mimic [...], especially when [...]."
   - "The discriminating feature is [...]."
5. Store only de-identified lessons. Do not store names, IDs, accession numbers, dates, or images containing protected health information.
6. Update the skill, reference notes, or memory when the lesson is broadly useful.

### Correction note template

```text
Correction note:
- Initial impression:
- Final diagnosis:
- Evidence for final diagnosis: pathology / surgery / follow-up / expert report / user feedback / literature
- Missed or underweighted imaging clue:
- Mimic/pitfall:
- Rule for next time:
- Suggested literature/reference to add:
```

The assistant should use accumulated corrections to improve future differential diagnosis and should explicitly mention relevant prior pitfalls when a similar pattern appears again.

## Response templates

### Concise clinical response
```text
Based on the provided images/video and clinical information, this is a limited interpretation because [...].

Clinical context used:
- Age/sex:
- Symptoms and duration:
- Physical exam/vitals:
- Laboratory tests:
- Prior imaging/pathology/endoscopy/treatment:

Key imaging findings:
1. ...
2. ...

Integrated impression:
1. Most likely diagnosis: ... (confidence: high/moderate/low)
   - Imaging basis: ...
   - Clinical/lab basis: ...
   - Key limitation: ...

Differential diagnoses to consider:
1. ... — supporting imaging/clinical features; features against; how to confirm/exclude
2. ... — supporting imaging/clinical features; features against; how to confirm/exclude
3. ... — supporting imaging/clinical features; features against; how to confirm/exclude

Urgent findings to exclude:
- ...

Evidence support:
- Source/citation if available:
- Why it supports the diagnosis:

Similar-case image comparison:
- Link if available:
- Similarities/differences:

Recommended next step:
- ...

Possible report wording:
...
```

### Teaching response
```text
The main imaging clue is [...].
This favors [...] because [...].
It is less typical for [...] because [...].
For similar cases, check: [...].
```

## Evidence and updating principles

When asked about criteria, staging, scores, or current evidence:
1. Prefer official guidelines, consensus statements, and established reporting systems.
2. Use high-quality review articles and major radiology references for imaging signs.
3. Use recent peer-reviewed literature for evolving topics such as AI, radiomics, and response prediction.
4. Do not claim comprehensive coverage of all books or all papers.
5. Label evidence strength and uncertainty where appropriate.
