AI-POWERED
SIMULATOR BUILD
WORKFLOW
	

	A step-by-step guide for instructional designers to use AI prompts to generate high-fidelity, interactive training simulators from screenshots.


ARAS LEARNING & DEVELOPMENT 
Internal Use Only
Do not copy, distribute, share or download without permission.
	WHAT THIS DOCUMENT IS


	

This guide provides a standardized prompt workflow for using AI (such as Claude or ChatGPT) to generate high-fidelity, self-contained training simulators from screenshots and written logic flows.
The output is a single HTML file that runs locally in any web browser. No server, no software installation, and no coding skills are required.


WHAT YOU WILL NEED BEFORE YOU START


	

Item
	Description
	Screenshots
	One screenshot per screen the learner will interact with during the simulation. Capture the full application window including navigation bars, toolbars, and sidebars.
	A Defined Goal
	A single sentence describing what the learner is trying to accomplish in the simulation (e.g., "Create a new Vendor Profile").
	A Written Logic Flow
	For each screenshot, a description of what the learner does, which element they interact with, and what happens next.
	

THE PROMPT TEMPLATE


	

Copy the full prompt below into your AI chat window using Gemini Canvas. Replace all bracketed [...] sections with your specific content. Then drag and drop your screenshots into the same message and send.


Global Goal: [INSERT GOAL HERE]

Persona: Expert Frontend Developer

Action: Build a high-fidelity, self-contained HTML/CSS/JS simulator
for training purposes based on the attached screenshots and the
logic flow below.


Context:
1. Visuals: Replicate the UI details from the screenshots exactly
   (colors, fonts, icon styles, and layout). If an element is in
   the image, it must be in the code.
2. Output: A single valid HTML code block that I can run locally.
3. Logic: Implement the following workflow:


Image 1 ([NAME OF SCREEN]): [DESCRIBE ACTION]
Image 2 ([NAME OF SCREEN]): [DESCRIBE ACTION]
Image 3 ([NAME OF SCREEN]): [DESCRIBE ACTION]
	



	What Do the Brackets Mean?
Every item in [SQUARE BRACKETS] is a placeholder. Replace it with your own content before sending the prompt.
Example: [INSERT GOAL HERE] becomes "Create a new Vendor Profile"
	

STEP-BY-STEP INSTRUCTIONS


	

Step 1: Capture Screenshots
Take one screenshot per distinct screen or state the learner will encounter during the simulation.
* Use full-screen or full-window captures. Do not crop out navigation bars, sidebars, or headers. The AI uses these elements to replicate the layout accurately.
* If a screen has an intermediate state (such as a dropdown opening or a modal appearing), capture that state as its own separate screenshot.
* Name your screenshots sequentially to keep them in order.




	Naming Example
01-Dashboard.png
02-AddVendorForm.png
03-ConfirmationMessage.png
	

Step 2: Write the Logic Flow
For each screenshot, write one concise statement that covers three things:
* What the learner does (the interaction: click, type, select)
* What element they interact with (be specific: button label, field name, menu item)
* What happens next (transition to the next screen, a modal appears, a message displays)




	Example Logic Flow
Global Goal: "Add a new supplier to the Approved Vendor List"


Image 1 (Vendor Dashboard): User clicks the "Add New Vendor" button in the top-right toolbar.
Image 2 (Vendor Form): User enters the Vendor Name and Vendor ID, then clicks "Save."
Image 3 (Confirmation Screen): A green success banner reads "Vendor saved successfully." End simulation.
	

Step 3: Assemble and Send
1. Open a new AI chat session.
2. Paste the full prompt template into the message box.
3. Replace all [...] placeholders with your content from Steps 1 and 2.
4. Drag and drop all screenshots into the same message.
5. Send.


Step 4: Review the Output
The AI will return a single block of HTML code. To test it:
1. Copy the entire code block.
2. Open a plain text editor (Notepad, VS Code, or TextEdit in plain text mode).
3. Paste the code and save the file with a .html extension (e.g., vendor-sim.html).
4. Open the file in a web browser (Chrome or Edge recommended).
5. Walk through the simulation and verify each interaction matches your logic flow.


WRITING EFFECTIVE LOGIC DESCRIPTIONS


	

The quality of the simulator depends directly on how clearly you describe the logic. The following principles will help you get the best results.
Be Specific About Interactive Elements


Weak Description
	Strong Description
	"User selects the button"
	"User selects the Save button in the bottom-right corner of the form"
	"User fills in the form"
	"User enters 'ACME Corp' in the Vendor Name field and '10042' in the Vendor ID field"
	"A message shows up"
	"A green banner appears at the top reading 'Record saved successfully'"
	Specify What Is and Is Not Interactive
If a screen has elements the learner should not select, say so explicitly. Otherwise, the AI may make everything selectable or may omit click targets you intended.


Image 2 (Order Form): Only the "Quantity" field and the "Submit"
button are interactive. All other fields are pre-filled and read-only.
	Describe Transitions Explicitly
State how the learner moves from one screen to the next. Do not assume the AI will infer the connection.


Image 1 (Home): User clicks "Reports" in the left sidebar.
This navigates to the Reports Dashboard (Image 2).
	Mark the End State
Always indicate which screen is the final state and what signals completion.


Image 4 (Confirmation): The confirmation dialog appears.
Simulation ends here. Display a "Restart" button to allow
the learner to try again.
	

TROUBLESHOOTING COMMON ISSUES


	

Problem
	What to Do
	Layout does not match screenshots
	Tell the AI exactly what is wrong: "The sidebar should be on the left, not the top. Refer to Image 1." Reattach the relevant screenshot.
	Missing interactive elements
	Specify: "The 'Cancel' button in Image 2 is not clickable. Make it functional — clicking it should return to Image 1."
	Colors or fonts are off
	Provide hex codes or describe precisely: "The header background is dark navy (#1B2A4A), not black."
	Simulation flow is wrong
	Restate the logic for the broken step. Confirm your Image numbering matches your descriptions.
	Code does not run
	Check that you saved the file with a .html extension and opened it in a modern browser. If output was truncated, ask: "The code appears incomplete. Please provide the full HTML file."
	AI produces multiple files
	Remind it: "Output must be a single self-contained HTML file. Inline all CSS and JavaScript."
	

USEFUL FOLLOW-UP PROMPTS


	

After the initial build, use these prompts to iterate and improve the simulator:


Goal
	Prompt to Send
	Fix a specific screen
	"Image 2 is not matching the screenshot. The form fields should be arranged in two columns, not one. Please update."
	Add guided hints
	"Add tooltip-style hints that appear when the learner hovers over the correct interactive element."
	Add error handling
	"If the learner clicks the wrong element, display a red-bordered tooltip that says 'Try clicking the Save button instead.'"
	Add a progress bar
	"Add a step indicator at the top showing which step the learner is on (e.g., Step 2 of 4)."
	Add a restart feature
	"Add a 'Start Over' button on the final screen that resets the simulation to Image 1."
	________________


KEY REMINDERS


	



	One simulation = one chat session. Starting a new simulation in a fresh session avoids context confusion from prior conversations.


More screenshots = better fidelity. If a screen has an intermediate state (such as a dropdown opening), capture that state as its own screenshot.


Test every interaction. Walk through the full simulation before sharing. Verify that every click target, field entry, and transition works as described.


Iterate, do not start over. If the first output is 80% correct, send targeted follow-up prompts to fix the remaining 20%. Do not regenerate from scratch.


Save your prompt. Keep a copy of your completed prompt alongside the final HTML file. This makes future updates straightforward.
	

FILE NAMING CONVENTION


	

Use the following format when saving simulator files:


[CourseID]-SIM-[ShortDescription]-v[Version].html
	

Examples: 
* PLME_U01-SIM-SearchClasses-v1.html
* PLME2_U05-SIM-MakeAPart-v2.html


QUESTIONS OR ISSUES


	

If you encounter a problem this document does not address, document the following and escalate:


1. The prompt you sent (copy the full text).
2. The screenshots you attached.
3. The AI output you received.
4. A description of what went wrong.


This information allows rapid troubleshooting and helps improve this workflow over time.