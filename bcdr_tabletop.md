# 🔄 BCDR Tabletop Simulation: Nuclear ICS Ransomware Response
*   **Regulatory Focus**: NERC CIP-008-6 (Incident Reporting & Response Planning), NIST SP 800-34 Rev. 1
*   **Target Infrastructure**: X-energy Advanced Reactor Digital Control Domain
*   **Exercise Coordinator**: Cybersecurity Analyst III

---

## 🎭 Scenario Inject: "Operation Cold Core"
An external software component utilized within the vendor platform modifies critical diagnostic system updates. At 04:00 EST, control room workstations experience system lag, followed by display lockouts showing an active enterprise ransomware payload demanding payment. 

### ⏱️ Primary Resilience Targets
*   **Recovery Time Objective (RTO)**: < 2 Hours for Safety Assessment telemetry data.
*   **Recovery Point Objective (RPO)**: < 15 Minutes of continuous historical sensor log loss.

---

## 📋 Phasewise Response Matrix

### Phase 1: Triage & Structural Isolation
*   **Immediate Action**: Activate the Incident Response Team (IRT) and pivot the operation to an emergency stand by state.
*   **OT Containment**: Disconnect the corporate IT active directories from the plant control layer proxy. Verify that the hardware **Data Diode** continues running in a strictly unidirectional state to prevent reverse packet traversal.
*   **Evidence Collection**: Take full forensic memory snapshots of the affected workstations before initiating system reboots.

### Phase 2: Vulnerability Analysis (Tenable & Splunk)
*   **Splunk Correlation**: Run high priority searches tracking the lateral movement of user authentication tokens. Map the root malicious execution vector to anomalous vendor service account sessions.
*   **Tenable Assessment**: Validate the patch posture of backup servers to ensure the payload cannot spread to isolated cold-standby configurations.

### Phase 3: Failover & Recovery Operations
*   **Cold Standby Activation**: Boot up the air-gapped, immutable infrastructure baseline configurations stored on write-once media.
*   **RPO Verification**: Re-ingest backup telemetry data up to the 03:45 EST milestone checkpoint. Verify that data loss does not exceed the target 15 minute barrier.
*   **RTO Validation**: Confirm that primary plant safety telemetry screens are fully functional and reporting real-time data within the 115 minute mark.

---

## 📈 Post-Incident Review Protocol
1.  **Vendor Debrief**: Revoke standing external access configurations for the compromised vendor platform. Mandate a full **SBOM** audit before restoring integration hooks.
2.  **Regulatory Notification**: Submit the formal cybersecurity incident report to the **E-ISAC** (Electricity Information Sharing and Analysis Center) and the **NRC** within the federally mandated 4-hour window per NERC CIP requirements.
