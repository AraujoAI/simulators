# AI-Powered Training Simulators

This repository contains browser-based training simulators generated from application screenshots using an AI prompt workflow. The simulators run locally as single HTML files and require no installation.

## What This Repo Contains

- Self-contained HTML simulators organized by business area (e.g., `training/`, `development/`, `marketing/`).
- A standardized AI prompt pattern for converting screenshots + logic flows into interactive simulations.
- Example file naming conventions and deployment patterns for GitHub Pages.

## High-Level Workflow

1. Capture one screenshot per screen/state in the target application.
2. Write a concise logic flow describing each action, target element, and resulting state.
3. Paste the prompt template into your AI assistant, attach screenshots, and send.
4. Save the returned HTML as `[CourseID]-SIM-[ShortDescription]-v[Version].html` and test in a browser.

For a detailed, internal-only guide, see `README_SIM.md` (Aras L&D access only).

## Prompt Template (Public-Safe Version)

Use this shortened template when working with an AI assistant:

> **Global Goal:** \[INSERT GOAL HERE]  
> **Persona:** Expert frontend developer  
> **Action:** Build a high-fidelity, single-file HTML/CSS/JS simulator from the screenshots and logic below.  
> **Constraints:**  
> - Replicate UI layout, colors, and key elements from screenshots.  
> - Output a single valid HTML file (inline CSS and JS).  
> - Implement the workflow:  
>   - Image 1 (\[NAME]): \[DESCRIBE ACTION]  
>   - Image 2 (\[NAME]): \[DESCRIBE ACTION]  
>   - Image 3 (\[NAME]): \[DESCRIBE ACTION]

Replace all items in square brackets with your specific goal, screen names, and actions.

## Authoring Guidelines (Summary)

- Be specific about interactive elements (button label, field name, location).
- Explicitly describe what is *not* interactive on each screen.
- Describe transitions between screens (“Click X, navigate to Image 2”).
- Mark the end state and what signals completion (e.g., confirmation banner + restart option).

See internal documentation for full examples and troubleshooting patterns.

## File Naming Convention

Save simulators using:

`[CourseID]-SIM-[ShortDescription]-v[Version].html`

Examples:

- `PLME_U01-SIM-SearchClasses-v1.html`
- `PLME2_U05-SIM-MakeAPart-v2.html`

## Questions or Issues

If a simulator does not behave as expected:

1. Save the prompt you used (including logic flow).
2. Save the screenshots you provided.
3. Save the AI-generated HTML file.
4. Document what is wrong and share with the L&D tools owner.
