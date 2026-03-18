# Candidate Submission Template

## Candidate Information
- Full Name: Jeneen Shaker
- Email:jeneenshaker@gmail.com
- LinkedIn or Portfolio: https://github.com/jeneen-shaker
- Submission Date: 16/Mar/26

## Overview
An automated end-to-end onboarding pipeline designed to transform raw employee intake data into personalized, role-specific 3-day onboarding plans. The system utilizes **n8n** as an orchestrator, **OpenAI** for intelligence, and **Airtable** for centralized operational tracking.

---

## Task 1: AI-Powered Automation Design

### Workflow Logic
1.  **Intake:** A new hire submits their details (Name, Department, Job Title) via a Google Form.
2.  **Trigger:** n8n monitors the linked Google Sheet and triggers the workflow upon a new row entry.
3.  **Context Construction:** The system extracts employee attributes to build a structured prompt.
4.  **AI Generation:** OpenAI (GPT-4o) processes the input to draft a tailored 3-day onboarding schedule.
5.  **Record Persistence:** n8n pushes the original data along with the AI-generated plan to Airtable.
6.  **Operational Sync:** The record is initialized with a "Started" status for HR review.

### Where AI Is Used
* **Classification:** Automatically identifying departmental needs to adjust the onboarding focus.
* **Automatic Drafting:** Generating complete, professional schedules without manual HR intervention.
* **Recommendations or Personalization:** Customizing technical tasks vs. cultural tasks based on the specific Job Title.

### Prompt Engineering
* **System/User Persona Pattern:** Established a "System Role" as an HR Expert to maintain tone, and a "User Role" for dynamic data injection.
* **Constraint Prompting:** Explicitly required Markdown formatting to ensure compatibility with Airtable's Rich Text fields.
* **Structured Output:** Enforced a 3-day chronological format to maintain consistency across all generated plans.

### Data Flow and Integrations
* **Google Workspace (Sheets):** Primary intake and trigger source.
* **n8n:** The central automation platform managing API orchestration and data mapping.
* **OpenAI:** The LLM engine providing logic and personalized content generation.
* **Airtable:** The central HRIS/Dashboard for data persistence and status tracking.

### Business Impact
* **Efficiency:** Reduces manual onboarding documentation time by approximately 90%.
* **Accuracy:** Ensures no critical steps are missed by using standardized AI templates.
* **New Hire Experience:** Provides a professional, "day-one ready" impression for every employee.
* **HR Focus:** Shifts HR's role from administrative drafting to high-value human interaction.

---

## Task 2: Implementation Demo

### Demo Type
* **n8n Workflow:** Exported JSON file.
* **Screenshots:** Visual proof of successful execution and data mapping.
* **Diagram:** Architecture flow representation.

### Files Included
* `starter/workflows/n8n_onboarding_workflow.json`
* `starter/screenshots/workflow_success.png`
* `starter/screenshots/airtable_output.png`
* `starter/design-solution.md`

### Flow of Data
Data flows linearly from **Google Sheets** (Input) ➔ **n8n** (Orchestrator) ➔ **OpenAI** (Processor) ➔ **Airtable** (Output/Storage). The mapping is performed manually within n8n to ensure high data fidelity.

### Pain Points Solved
It eliminates **"Generic Onboarding Syndrome"** where new hires receive irrelevant tasks. It also solves **"Data Fragmentation"** by ensuring all onboarding data is stored in a single, trackable database instead of disparate emails or forms.

---

## Assumptions
* The system assumes that the "Department" and "Job Title" fields are provided to ensure effective AI personalization.
* It is assumed that HR will manually update the 'Status' in Airtable once they have finalized the hardware/IT setup for the new hire.

## Setup Instructions
1.  Import the `n8n_onboarding_workflow.json` into your n8n instance.
2.  Configure credentials for **Google Sheets**, **OpenAI**, and **Airtable**.
3.  In Airtable, ensure the `AI Onboarding Plan` field is set to **Long Text** with **Rich Text** enabled.
4.  Execute the workflow and submit a test entry in the linked Google Sheet.
