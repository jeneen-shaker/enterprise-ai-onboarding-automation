graph LR
    A[Google Forms/Sheets] --> B{n8n Orchestrator}
    B --> C[OpenAI GPT-4o]
    C --> B
    B --> D[Airtable Dashboard]
    
    style B fill:#f96,stroke:#333,stroke-width:4px
    style C fill:#00a,stroke:#333,stroke-width:2px,color:#fff