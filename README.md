# Power BI – Embedded Report Flow (Mermaid Diagram)

Below is a flowchart explaining the Power BI SDK report customization and loading process.

```mermaid
flowchart TD
  subgraph Portal_Web_App_SDK["Portal Web App SDK"]
        A[1. User customizes visual]
        B{2. Click on Save State}
        C[3. Client SDK calls API to get JSON]
        D[4. Captures the complete JSON object]
  end

  subgraph External_Storage["External Storage"]
        E[5. Database stores JSON]
  end

  subgraph Report_Loading["Report Loading"]
        F[6. User loads report]
  end

  subgraph Power_BI_Service["Power BI Service"]
        G[7. Central semantic model]
        J[10. Embedded report with full customization]
  end

  A --> B
  B --> C
  C --> D
  D --> E
  F --> H[8. Retrieves stored JSON]
  E --> H
  H --> I[9. Client SDK applies JSON - setReportState]
  I --> G
  G --> J

  style Portal_Web_App_SDK fill:#e0f3ff,stroke:#007acc,stroke-width:2px,color:#000,font-weight:bold
  style External_Storage fill:#eaffea,stroke:#33a02c,stroke-width:2px,color:#000
  style Report_Loading fill:#fff3cd,stroke:#e6b800,stroke-width:2px,color:#000
  style Power_BI_Service fill:#fff0f5,stroke:#cc6699,stroke-width:2px,color:#000
  style B fill:#f9f,stroke:#333,stroke-width:2px

