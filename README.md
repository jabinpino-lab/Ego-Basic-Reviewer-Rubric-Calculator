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

## Desktop app (Windows, macOS, Linux)

This project includes an Electron desktop wrapper so the calculator can be packaged as installable software.

1. Install Node.js (LTS).
2. Download or clone this repository.
3. In the project folder, run:

   ```bash
   npm install
   npm run desktop
   ```

   This builds the web app and opens it in an Electron desktop window.

### Download the Windows and macOS apps

The GitHub Actions workflow builds both desktop versions automatically when code is pushed to `main`, and can also be started manually:

1. Open the repository's **Actions** tab and select **Build Desktop App**.
2. Choose **Run workflow** to start a build.
3. After both jobs finish, open the workflow run's **Artifacts** section.
4. Download `windows-installers` for the Windows `.exe` installer / portable app, or `macos-installer` for the macOS `.dmg` installer.

To publish downloadable installers on a GitHub Release, create and push a version tag such as `v1.0.1`. The workflow builds both platforms and attaches their installers to that release.

### Build locally

- Windows: `npm run desktop:dist` creates Windows installer and portable builds in `release/`.
- macOS: `npm run desktop:dist` creates a DMG in `release/` (build on macOS).

Build each installer on its target operating system. The calculator runs locally in the desktop window and does not require a hosted website for its core calculation. macOS signing and notarization are not configured yet, so macOS may show a security warning when opening the app.
