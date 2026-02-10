

| ![][image1] AI-POWERED SIMULATOR BUILD WORKFLOW |
| ----- |
|  |
| A step-by-step guide for instructional designers to use AI prompts to generate high-fidelity, interactive training simulators from screenshots. **ARAS LEARNING & DEVELOPMENT**  Internal Use Only Do not copy, distribute, share or download without permission. |

**WHAT THIS DOCUMENT IS**

|  |
| :---- |

This guide provides a standardized prompt workflow for using AI (such as Claude or ChatGPT) to generate high-fidelity, self-contained training simulators from screenshots and written logic flows.

The output is a single HTML file that runs locally in any web browser. No server, no software installation, and no coding skills are required.

**WHAT YOU WILL NEED BEFORE YOU START**

|  |
| :---- |

| Item | Description |
| :---- | :---- |
| **Screenshots** | One screenshot per screen the learner will interact with during the simulation. Capture the full application window including navigation bars, toolbars, and sidebars. |
| **A Defined Goal** | A single sentence describing what the learner is trying to accomplish in the simulation (e.g., "Create a new Vendor Profile"). |
| **A Written Logic Flow** | For each screenshot, a description of what the learner does, which element they interact with, and what happens next. |

**THE PROMPT TEMPLATE**

|  |
| :---- |

Copy the full prompt below into your AI chat window using Gemini Canvas. Replace all bracketed \[...\] sections with your specific content. Then drag and drop your screenshots into the same message and send.

| Global Goal: \[INSERT GOAL HERE\]Persona: Expert Frontend Developer Action: Build a high-fidelity, self-contained HTML/CSS/JS simulator for training purposes based on the attached screenshots and the logic flow below. Context: 1\. Visuals: Replicate the UI details from the screenshots exactly    (colors, fonts, icon styles, and layout). If an element is in    the image, it must be in the code. 2\. Output: A single valid HTML code block that I can run locally. 3\. Logic: Implement the following workflow: Image 1 (\[NAME OF SCREEN\]): \[DESCRIBE ACTION\] Image 2 (\[NAME OF SCREEN\]): \[DESCRIBE ACTION\] Image 3 (\[NAME OF SCREEN\]): \[DESCRIBE ACTION\] |
| :---- |

|  | What Do the Brackets Mean? Every item in \[SQUARE BRACKETS\] is a placeholder. Replace it with your own content before sending the prompt. Example: \[INSERT GOAL HERE\] becomes "Create a new Vendor Profile" |
| :---- | :---- |

**STEP-BY-STEP INSTRUCTIONS**

|  |
| :---- |

**Step 1: Capture Screenshots**

Take one screenshot per distinct screen or state the learner will encounter during the simulation.

* Use full-screen or full-window captures. Do not crop out navigation bars, sidebars, or headers. The AI uses these elements to replicate the layout accurately.

* If a screen has an intermediate state (such as a dropdown opening or a modal appearing), capture that state as its own separate screenshot.

* Name your screenshots sequentially to keep them in order.

|  | Naming Example 01-Dashboard.png 02-AddVendorForm.png 03-ConfirmationMessage.png |
| :---- | :---- |

**Step 2: Write the Logic Flow**

For each screenshot, write one concise statement that covers three things:

* **What the learner does** (the interaction: click, type, select)

* **What element they interact with** (be specific: button label, field name, menu item)

* **What happens next** (transition to the next screen, a modal appears, a message displays)

|  | Example Logic Flow Global Goal: "Add a new supplier to the Approved Vendor List" Image 1 (Vendor Dashboard): User clicks the "Add New Vendor" button in the top-right toolbar. Image 2 (Vendor Form): User enters the Vendor Name and Vendor ID, then clicks "Save." Image 3 (Confirmation Screen): A green success banner reads "Vendor saved successfully." End simulation. |
| :---- | :---- |

**Step 3: Assemble and Send**

1. Open a new AI chat session.

2. Paste the full prompt template into the message box.

3. Replace all \[...\] placeholders with your content from Steps 1 and 2\.

4. Drag and drop all screenshots into the same message.

5. Send.

**Step 4: Review the Output**

The AI will return a single block of HTML code. To test it:

1. Copy the entire code block.

2. Open a plain text editor (Notepad, VS Code, or TextEdit in plain text mode).

3. Paste the code and save the file with a **.html** extension (e.g., vendor-sim.html).

4. Open the file in a web browser (Chrome or Edge recommended).

5. Walk through the simulation and verify each interaction matches your logic flow.

**WRITING EFFECTIVE LOGIC DESCRIPTIONS**

|  |
| :---- |

The quality of the simulator depends directly on how clearly you describe the logic. The following principles will help you get the best results.

**Be Specific About Interactive Elements**

| Weak Description | Strong Description |
| :---- | :---- |
| "User selects the button" | "User selects the **Save** button in the bottom-right corner of the form" |
| "User fills in the form" | "User enters 'ACME Corp' in the **Vendor Name** field and '10042' in the **Vendor ID** field" |
| "A message shows up" | "A green banner appears at the top reading 'Record saved successfully'" |

**Specify What Is and Is Not Interactive**

If a screen has elements the learner should not select, say so explicitly. Otherwise, the AI may make everything selectable or may omit click targets you intended.

| Image 2 (Order Form): Only the "Quantity" field and the "Submit" button are interactive. All other fields are pre-filled and read-only. |
| :---- |

**Describe Transitions Explicitly**

State how the learner moves from one screen to the next. Do not assume the AI will infer the connection.

| Image 1 (Home): User clicks "Reports" in the left sidebar. This navigates to the Reports Dashboard (Image 2). |
| :---- |

**Mark the End State**

Always indicate which screen is the final state and what signals completion.

| Image 4 (Confirmation): The confirmation dialog appears. Simulation ends here. Display a "Restart" button to allow the learner to try again. |
| :---- |

**TROUBLESHOOTING COMMON ISSUES**

|  |
| :---- |

| Problem | What to Do |
| :---- | :---- |
| **Layout does not match screenshots** | Tell the AI exactly what is wrong: "The sidebar should be on the left, not the top. Refer to Image 1." Reattach the relevant screenshot. |
| **Missing interactive elements** | Specify: "The 'Cancel' button in Image 2 is not clickable. Make it functional — clicking it should return to Image 1." |
| **Colors or fonts are off** | Provide hex codes or describe precisely: "The header background is dark navy (\#1B2A4A), not black." |
| **Simulation flow is wrong** | Restate the logic for the broken step. Confirm your Image numbering matches your descriptions. |
| **Code does not run** | Check that you saved the file with a .html extension and opened it in a modern browser. If output was truncated, ask: "The code appears incomplete. Please provide the full HTML file." |
| **AI produces multiple files** | Remind it: "Output must be a single self-contained HTML file. Inline all CSS and JavaScript." |

**USEFUL FOLLOW-UP PROMPTS**

|  |
| :---- |

After the initial build, use these prompts to iterate and improve the simulator:

| Goal | Prompt to Send |
| :---- | :---- |
| **Fix a specific screen** | "Image 2 is not matching the screenshot. The form fields should be arranged in two columns, not one. Please update." |
| **Add guided hints** | "Add tooltip-style hints that appear when the learner hovers over the correct interactive element." |
| **Add error handling** | "If the learner clicks the wrong element, display a red-bordered tooltip that says 'Try clicking the Save button instead.'" |
| **Add a progress bar** | "Add a step indicator at the top showing which step the learner is on (e.g., Step 2 of 4)." |
| **Add a restart feature** | "Add a 'Start Over' button on the final screen that resets the simulation to Image 1." |

**KEY REMINDERS**

|  |
| :---- |

|  | One simulation \= one chat session. Starting a new simulation in a fresh session avoids context confusion from prior conversations. More screenshots \= better fidelity. If a screen has an intermediate state (such as a dropdown opening), capture that state as its own screenshot. Test every interaction. Walk through the full simulation before sharing. Verify that every click target, field entry, and transition works as described. Iterate, do not start over. If the first output is 80% correct, send targeted follow-up prompts to fix the remaining 20%. Do not regenerate from scratch. Save your prompt. Keep a copy of your completed prompt alongside the final HTML file. This makes future updates straightforward. |
| :---- | :---- |

**FILE NAMING CONVENTION**

|  |
| :---- |

Use the following format when saving simulator files:

| \[CourseID\]-SIM-\[ShortDescription\]-v\[Version\].html |
| :---- |

**Examples:** 

* PLME\_U01-SIM-SearchClasses-v1.html

* PLME2\_U05-SIM-MakeAPart-v2.html

**QUESTIONS OR ISSUES**

|  |
| :---- |

If you encounter a problem this document does not address, document the following and escalate:

1. The prompt you sent (copy the full text).

2. The screenshots you attached.

3. The AI output you received.

4. A description of what went wrong.

This information allows rapid troubleshooting and helps improve this workflow over time.

[image1]: <data:image/png;base64,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ERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERHNjv8Dls5FlB9j/p4AAAAASUVORK5CYII=>