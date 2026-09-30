# EGO Basic Reviewer Rubric Calculator

A responsive React + Vite calculator for the EGO Basic Reviewer Rubric. Enter minor/major error counts for Event Length, Verb Selection, Event Segmentation, Description, and Clip Export to see dimension stars, the overall grade, and Accept/Reject status.

## Run locally

```bash
npm install
npm run dev
```

Build with `npm run build`.

## Calculation behavior

- Five dimensions are equally weighted; overall score is the arithmetic mean rounded to one decimal.
- Accept when every dimension is at least 3 stars; reject if any dimension is 1 or 2.
- More than 5 consecutive identical subgoals automatically sets the result to 1 star and produces the required feedback: “More than 5 consecutive identical subgoals”.
- Feedback can be copied for the audit record.

Thresholds are implemented from the supplied rubric. Some ranges in the source rubric are not explicitly defined; verify local interpretations for boundary cases.