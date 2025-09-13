*Automated Diagram Generation & Refinement*

Problem Statement
-----------------
The goal of this assignment is to build a Python program that:
1. Accepts a natural language query (e.g., "Create a flowchart for a login page").
2. Generates a Mermaid diagram (.mmd) using the Gemini API.
3. Attempts to render the diagram into a PNG using Mermaid CLI.
4. Iteratively refines the diagram for N iterations (default = 3), fixing errors or improving clarity.
5. Saves all intermediate .mmd files for traceabilit

------------------------------------------------------------

Setup Instructions
------------------

1. Clone/Extract the project
   cd main

2. Install Python dependencies
   pip install -r requirements.txt

3. Install Mermaid CLI (for rendering .mmd → .png)
   npm install -g @mermaid-js/mermaid-cli

4. Set your Gemini API Key
   Replace "your_api_key_here" with your actual Gemini API key.

   On Google Colab (inside a cell):
   import os
   os.environ["GEMINI_API_KEY"] = "your_api_key_here"

------------------------------------------------------------

Running the Program
-------------------

Run the script:
   python main.py

You will be prompted:
   Query: Create a simple flowchart for a user login process.
   Maximum refinement iterations (default 3): 3

The program will:
- Generate an initial Mermaid diagram.
- Try to render it with mmdc.
- If errors occur, send them back for correction.
- Continue refining for up to N iterations.
- Save all .mmd versions

------------------------------------------------------------

Output Files
------------

Inside the output/ folder, you will find:
- output.mmd → initial Mermaid diagram
- output_iter_1.mmd, output_iter_2.mmd, output_iter_3.mmd → refinement iterations
- output_iter_3.png → final refined PNG diagram

------------------------------------------------------------

Features Implemented
--------------------
- Natural language → Mermaid diagram pipeline.
- Configurable refinement iterations (N, default 3).
- Automatic error detection + iterative improvement.
- Robust JSON parsing (extracts only valid JSON from model output).
- Boolean normalization for schema validation.
- Retry mechanism for Gemini API (503 Service Unavailable handling).
- Saves .mmd at each iteration for traceability.

------------------------------------------------------------


