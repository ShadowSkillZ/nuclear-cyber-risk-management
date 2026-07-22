# ⚛️ Nuclear Cybersecurity Risk Framework & Portfolio Simulation

An advanced cybersecurity risk portfolio detailing critical infrastructure protections tailored to commercial clean energy and nuclear generation plants. This repository models cross-functional technical compliance tracking frameworks across Risk & Audits, Software Supply Chain Vetting, and Industrial BCDR Planning.

## 📜 Regulatory Standards Mapping
*   **10 CFR 73.54**: Protection of digital computer and communication systems.
*   **NRC RG 5.71 / NEI 08-09**: Nuclear Regulatory Commission frameworks for Critical Digital Assets (CDAs).
*   **NERC CIP**: Mandatory security controls for systems tied to the bulk electric infrastructure.
*   **NIST SP 800-53 & SP 800-82**: Security controls for federal IT systems and industrial Operational Technology (OT/ICS).

## 📁 Repository Structure
*   📊 `2026_assessment.csv`: Interactive threat gap matrix detailing asset scanning and software provenance deficiencies.
*   🗄️ `register.json`: Machine-readable risk ledger database scoring inherent versus residual risk metrics.

## 📐 Nuclear Architecture Data Diode & SIEM Flow
```mermaid
graph TD
    %% Define styles
    classDef ot fill:#ff9999,stroke:#333,stroke-width:2px;
    classDef it fill:#99ccff,stroke:#333,stroke-width:2px;
    classDef sec fill:#ffff99,stroke:#333,stroke-width:2px;

    subgraph OT_Control_Network [Nuclear Plant OT Network - High Security]
        A[Control Room Endpoints] -->|Auth Logs| B(Tenable OT Security Passive Monitor)
    end
    
    subgraph Air_Gap_Isolation [Hardware Isolation Protocol]
        B -->|Unidirectional Fiber Link| C[Data Diode Gateway]
    end

    subgraph Corporate_IT_Network [Enterprise Network Environment]
        C -->|Secure Log Relay| D[(Central Splunk SIEM Cluster)]
        E[MFA Authenticated Vendor Session] -->|Zero Trust Proxy| D
    end

    %% Apply Styles
    class A,B ot;
    class C sec;
    class D,E it;
```

> *Architecture Note: This diagram outlines the unidirectional security boundary separating the high security nuclear plant OT environment from the corporate Splunk SIEM via hardware data diodes.*
