# Task 1: Prompt Engineering & AI Logic

## 🎯 Objective
To design a robust and context-aware prompt system that generates personalized 3-day onboarding plans based on employee data (Name, Department, Job Title).

## 🧠 Prompt Architecture
I utilized a **System/User dual-prompt architecture** to ensure the AI maintains a professional persona while processing dynamic data accurately.

### 1. System Prompt (The Persona)
> **Role:** Expert HR Operations Assistant
> **Instruction:** "You are an expert HR Operations Assistant specialized in enterprise onboarding. Your goal is to create structured, professional, and welcoming onboarding plans. Always return the output in a clear, bulleted Markdown format."

### 2. User Prompt (The Dynamic Input)
> **Instruction:** "Please generate a 3-day onboarding plan for a new hire with the following details:
> - Name: {{ $json['Full Name'] }}
> - Department: {{ $json['Department'] }}
> - Job Title: {{ $json['Job Title'] }}
> The plan should include technical setup for their specific department, key meetings, and cultural integration."

## 🛠️ Key Design Principles
* **Context Awareness:** By passing the 'Department' field, the AI tailors specific tasks (e.g., GitHub access for Engineers, CRM training for Sales).
* **Formatting Control:** Explicitly requesting "Bulleted Markdown" ensures the output is ready for Rich Text rendering in Airtable.
* **Scalability:** The template works for any role without needing to rewrite the logic.