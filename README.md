

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
