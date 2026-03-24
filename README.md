# Enterprise AI Onboarding Orchestrator 

An automated, end-to-end system designed to streamline employee intake, generate personalized role-specific onboarding journeys using LLMs, and centralize data for HR operational excellence.

## Architecture Overview
The system follows a modular "Intake-Processor-Storage" architecture:
1.  **Intake (Source of Truth):** Google Forms & Sheets for structured data collection.
2.  **Intelligence (The Brain):** OpenAI GPT-4o integration via n8n to generate context-aware onboarding plans.
3.  **Operations (The Dashboard):** Airtable for centralized tracking, status management, and HR visibility.

## Key Features & AI Logic
* **Dual-Prompt Engineering:** Implemented a System/User role architecture to ensure the AI maintains a professional "HR Expert" persona while processing dynamic employee data.
* **Role-Based Personalization:** The system automatically tailors the 3-day plan based on the department (e.g., Engineering vs. Sales), ensuring relevant technical and cultural integration.
* **Human-in-the-Loop:** Designed with a 'Status' field in Airtable to allow HR review and quality assurance before finalizing plans.

##Technology Stack
* **Orchestration:** n8n (Workflow Automation)
* **LLM:** OpenAI (GPT-4o)
* **Database:** Airtable
* **Input Layer:** Google Workspace

## Project Structure
* `/solutions`: 
    * `task1_solution.md`: Detailed breakdown of Prompt Engineering & Logic.
    * `task2_solution.md`: Technical documentation of the workflow implementation.
* `/assets`: Screenshots of the successful n8n workflow and Airtable output.
* `n8n_workflow.json`: The exported workflow file for technical review.

## Scalability & Future Roadmap
* **Scalability:** The architecture is designed to handle high-volume hiring without manual intervention.
* **Security:** Credentials are managed securely within n8n's environment.
* **Next Steps:** Integration with Slack for instant HR notifications and automated email delivery of the generated plans to new hires.
