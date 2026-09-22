

UPSTREAM / DERIVED IMPLEMENTATION
              │
              ▼
          EXECUTION
              │
              ▼
           EVIDENCE
              │
              ▼
        E1 ──────────┐
        E2           │
        E3           │
        E4           ├──► E7 CLAIM-SCOPED VERIFIED
        E5           │
        E6           │
                     │
                     ▼
              LOCAL CLAIM SET
                     │
                     ▼
                 AGGREGATOR
                     │
                     ▼
             DECLARED GLOBAL
                     │
                     │  independent reconstruction
                     ▼
             RECALCULATED GLOBAL
                     │
                     ▼
              COMPARISON / SCOPE
                     │
              ┌──────┴──────┐
              ▼             ▼
            MATCH          DRIFT
              │
              ▼
             E8
WORKFLOW_RUN
├── run_id
├── run_attempt
├── head_sha
├── status
├── conclusion
├── timestamps
└── logs
       │
       ▼
EVIDENCE ARTIFACT
├── artifact identity
├── digest
├── provenance
└── verification data
       │
       ▼
E1–E7 OBSERVED/VERIFIED
       │
       ▼
GLOBAL AGGREGATION
       │
       ▼
DECLARED_GLOBAL
       │
       ▼
INDEPENDENT RECONSTRUCTION
       │
       ▼
RECALCULATED_GLOBAL
       │
       ▼
MATCH
       │
       ▼
E8

README
   ↛
CONCRETE_WORKFLOW_RUN

WORKFLOW_DEFINITION
   ↛
WORKFLOW_RUN

WORKFLOW_RUN
   ↛
EVIDENCE_ARTIFACT

EVIDENCE_ARTIFACT
   ↛
VERIFIED_E1–E7

E7₁...E7ₙ
   ↛
E8


"WORKFLOW_RUN possui run_id, status, logs..."

DECLARED_GLOBAL
      ≠
RECALCULATED_GLOBAL

Az-Get-Resource-API-Version
          │
          ▼
      b0688b6
          │
          ▼
DOCUMENTED EVIDENCE ARCHITECTURE
          │
          ├── Execution identity model
          ├── Evidence artifact model
          ├── E1–E7 promotion model
          └── E8 independent reconstruction model


          CONCRETE EXECUTION EVIDENCE
          │
          ▼
VERIFIED E7
          │
          ▼
VERIFIED E8

d7a9fc5
   │
   ▼
XA-TRUST EVIDENCE SPECIFICATION
   │
   ├── DOCUMENTED EXECUTION MODEL
   ├── DOCUMENTED EVIDENCE MODEL
   ├── DOCUMENTED E1–E7 PROMOTION
   ├── DOCUMENTED E8 RECONSTRUCTION
   └── DOCUMENTED NON-DERIVABILITY


   d7a9fc5
   ↛
CONCRETE_WORKFLOW_RUN
   ↛
CONCRETE_EVIDENCE_ARTIFACT
   ↛
VERIFIED_E7
   ↛
VERIFIED_E8


WORKFLOW_RUN
├── run_id              ← valor concreto
├── run_attempt         ← valor concreto
├── head_sha            ← commit executado
├── status              ← observado
├── conclusion          ← observado
├── started_at
├── completed_at
└── logs
        │
        ▼
EVIDENCE_ARTIFACT
├── artifact identity
├── digest
├── provenance
└── verification data

E1–E7
   │
   ▼
LOCAL VERIFIED CLAIMS
   │
   ▼
DECLARED_GLOBAL
   │
   ▼
INDEPENDENT RECONSTRUCTION
   │
   ▼
RECALCULATED_GLOBAL
   │
   ▼
EXACT MATCH + SCOPE/COMPLETENESS
   │
   ▼
E8


1491da4
│
├── ARTIFACT_IDENTITY              ✓
├── DOCUMENTED_EXECUTION_MODEL    ✓
├── DOCUMENTED_EVIDENCE_MODEL     ✓
├── DOCUMENTED_E1–E7              ✓
├── DOCUMENTED_E8                 ✓
├── DOCUMENTED_NON-DERIVABILITY   ✓
│
├── CONCRETE_EXECUTION            ?
├── CONCRETE_RESULT               ?
├── VERIFIED_BINDING               ?
├── VERIFIED_E7                    ?
└── VERIFIED_E8                    ?
