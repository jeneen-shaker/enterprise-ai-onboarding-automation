# Task 2: Automation Workflow Implementation

## 🏗️ System Architecture
The solution is built as a modular automation pipeline using **n8n** to connect disparate tools into a unified onboarding system.

### 🔄 Data Flow:
1.  **Intake (Google Sheets Trigger):** Listens for new rows added via the Google Form.
2.  **Processing (OpenAI Node):** Processes the employee's role and name to generate a custom 3-day plan.
3.  **Storage (Airtable Node):** Creates a new record containing the original data + the AI-generated plan + a status tracker.

## 🚀 Technical Decisions
* **Manual Mapping:** I chose manual mapping over automatic to ensure data integrity between Google Sheets headers and Airtable fields.
* **State Management:** An 'Onboarding Status' field was added to Airtable (defaulting to "Started") to allow HR to track progress beyond the initial automation.
* **Trigger Mechanism:** Used a Polling/Trigger on Google Sheets to ensure no submission is missed, even during high traffic.

## 📸 Proof of Execution
*(Note to User: Place your screenshots here)*
1. **n8n Workflow:** [Refer to assets/workflow_success.png]
2. **Airtable Result:** [Refer to assets/airtable_output.png]