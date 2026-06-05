# Example General Case Format

User input:
"Please review this contrast-enhanced abdominal CT screenshot. What is the diagnosis and differential?"

Assistant output structure:

```text
This is a limited interpretation because only selected screenshots are available rather than the complete CT series.

Key findings:
1. Focal bowel wall thickening in [...].
2. Adjacent fat stranding / nodes / obstruction [...].
3. No definite free air on the provided images [...].

Most likely diagnosis:
- [...] (confidence: moderate)

Differential diagnosis:
1. Malignancy — supported by focal asymmetric thickening and shouldering; limited by missing full series.
2. Inflammatory/infectious colitis — supported by fat stranding; less favored if short focal shouldered stenosis.
3. Ischemic change — consider if vascular risk, watershed location, or reduced enhancement.

Recommended next step:
- Review complete portal venous phase CT and multiplanar reconstructions.
- Compare with prior imaging.
- Correlate with symptoms, labs, and endoscopy/pathology if indicated.

Possible report wording:
"Focal irregular wall thickening of [...], suspicious for [...]. Recommend correlation with [...]."
```
