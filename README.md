README.md
│
├── DOCUMENTED XA-TRUST EXECUTION MODEL
│   ├── E3 — EXECUTION IDENTITY
│   ├── E4 — OBSERVED RESULT
│   ├── E5 — BINDING / INTEGRITY
│   ├── E6 — INDEPENDENT VERIFICATION
│   ├── E7 — CLAIM-SCOPED VERIFIED
│   └── E8 — GLOBAL VERIFICATION
│
└── DOES NOT ITSELF ESTABLISH
    ├── CONCRETE WORKFLOW RUN
    ├── CONCRETE EXECUTION RESULT
    ├── VERIFIED BINDING
    ├── E7
    └── E8

    FROZEN — XA-TRUST GITHUB WORKFLOW EXECUTION MODEL

WORKFLOW DEFINITION
        ↓
TRIGGER CONFIGURATION
        ↓
TRIGGER EVENT
        ↓
event.workflow_run.id
        ↓
EXACT RUN RESOLUTION
        ↓
GET /actions/runs/{RUN_ID}
        ↓
run.id === event.workflow_run.id
        ↓
RUN IDENTITY VALID
        ↓
E3 — EXECUTION_EVENT_EVIDENCE
        ├── repository
        ├── workflow
        ├── workflow_path
        ├── run_id
        ├── run_attempt
        ├── head_sha
        ├── event
        ├── temporal context
        ├── status
        └── conclusion
        ↓
JOB / STEP EXECUTION
        ↓
E4 — OBSERVED RESULT EVIDENCE
        ↓
E5 — BINDING / INTEGRITY
        ↓
E6 — INDEPENDENT VERIFICATION
        ↓
APPLICABLE PROMOTION POLICY
        ↓
E7 — CLAIM-SCOPED VERIFIED


WORKFLOW DEFINITION
        ↓
TRIGGER
        ↓
CONCRETE RUN
        ↓
E3
        ↓
OBSERVED RESULT
        ↓
E4
        ↓
BINDING / INTEGRITY
        ↓
E5
        ↓
INDEPENDENT VERIFICATION
        ↓
E6
        ↓
PROMOTION POLICY
        ↓
E7 — CLAIM-SCOPED VERIFIED
        ↓
EXPLICIT GLOBAL CONTRACT
        ↓
INDEPENDENT RECONSTRUCTION
        ↓
E8 — GLOBAL VERIFICATION


README ⇏ CONCRETE_WORKFLOW_RUN

WORKFLOW_DEFINITION ⇏ WORKFLOW_RUN

COMMIT_MESSAGE ⇏ EXECUTION_VERIFIED

WORKFLOW_RUN_COMPLETED ⇏ TEST_PASSED

WORKFLOW_CONCLUSION_SUCCESS ⇏ CLAIM_CONFORMANCE

WORKFLOW_SUCCESS ⇏ CONCRETE_API_EXECUTION

HASH_VALID ⇏ SEMANTIC_CORRECTNESS

MERKLE_VALID ⇏ CLAIM_TRUTH

E5 ⇏ E7

E7(CLAIM-X, SCOPE-X) ⇏ E7(CLAIM-Y, SCOPE-Y)

E7 ⇏ GLOBAL_VERIFIED



    FROZEN — XA-TRUST GITHUB WORKFLOW EXECUTION MODEL

gh workflow run <workflow-file>.ymlWORKFLOW DEFINITION
        │
        ▼
TRIGGER CONFIGURATION
        │
        │  ⇏ CONCRETE RUN
        ▼
TRIGGER EVENT
        │
        ├── actor = cyrillofrancisco30-lgtm
        ├── event = workflow_dispatch / push / ...
        └── event identity
        │
        ▼
event.workflow_run.id
        │
        ▼
EXACT RUN RESOLUTION
        │
        ▼
run.id === event.workflow_run.id
        │
        ▼
RUN IDENTITY VALID
        │
        ▼
E3 — EXECUTION_EVENT_EVIDENCE
        │
        ├── repository
        ├── workflow
        ├── workflow_path
        ├── run_id
        ├── run_attempt
        ├── head_sha
        ├── temporal context
        ├── status
        └── conclusion
        │
        ▼
JOB / STEP EXECUTION
        │
        ▼
E4 — OBSERVED RESULT EVIDENCE
        │
        ▼
E5 — BINDING / INTEGRITY
        │
        ▼
E6 — INDEPENDENT VERIFICATION
        │
        ▼
APPLICABLE PROMOTION POLICY
        │
        ▼
E7 — CLAIM-SCOPED VERIFIED

gh run list --limit 5


RUN_ID
  ↓
GET /actions/runs/{RUN_ID}
  ↓
run.id === RUN_ID
  ↓
E3 — EXECUTION IDENTITY
  ↓
GET /actions/runs/{RUN_ID}/jobs
  ↓
JOB_ID
  ↓
STEP_ID
  ↓
gh run view {RUN_ID} --log
  ↓
COMMAND_INVOCATION_OBSERVED
  ↓
API_REQUEST_OBSERVED
  ↓
HTTP_RESPONSE_OBSERVED
  ↓
SAME_EXECUTION_BINDING
  ↓
RESULT_OBSERVATION_VALID
  ↓
E4 — OBSERVED API RESULT

[ Disparar workflow ]


TRIGGER
  ≠
EXECUTION
  ≠
RESULT
  ≠
BINDING
  ≠
INDEPENDENT VERIFICATION
  ≠
CLAIM
  ≠
GLOBAL STATE

disparar workflow 


E7 LOCAL CLAIM SET
        ↓
DEFINED GLOBAL SCOPE
        ↓
COVERAGE / COMPLETENESS
        ↓
DECLARED GLOBAL
        ↓
INDEPENDENT RECONSTRUCTION
        ↓
RECALCULATED GLOBAL
        ↓
EXACT MATCH
        ↓
INDEPENDENT GLOBAL VERIFICATION
        ↓
GLOBAL PROMOTION POLICY
        ↓
E8


cyrillofrancisco30-lgtm
        ⇏
WORKFLOW_SUCCESS

WORKFLOW_TRIGGERED
        ⇏
WORKFLOW_SUCCESS

WORKFLOW_SUCCESS
        ⇏
TEST_PASSED

WORKFLOW_SUCCESS
        ⇏
CONCRETE_API_EXECUTION

WORKFLOW_SUCCESS
        ⇏
CLAIM-SCOPED VERIFIED

CLAIM-SCOPED VERIFIED
        ⇏
GLOBAL_VERIFIED


disparar workflow 

WORKFLOW: "Step 0, Start"
        │
        ├── TRIGGER
        │     ├── workflow_dispatch
        │     └── push → main
        │
        ├── PERMISSIONS
        │     ├── contents: write
        │     └── pull-requests: write
        │
        ├── JOB
        │     └── on_start
        │           ├── if: !repository.is_template
        │           └── ubuntu-latest
        │
        ├── STEPS
        │     ├── Checkout
        │     ├── Create branch / files / commit / push
        │     ├── Create Pull Request
        │     └── Update step 0 → 1
        │
        └── EXECUTION
              └── NOT ESTABLISHED BY YAML ALONE

COMMIT 8455fba
        ↓
README.md
        ↓
DOCUMENTED XA-TRUST EXECUTION MODEL



E3 — EXECUTION IDENTITY
E4 — OBSERVED RESULT
E5 — BINDING / INTEGRITY
E6 — INDEPENDENT VERIFICATION
E7 — CLAIM-SCOPED VERIFIED
E8 — GLOBAL VERIFICATION


README
⇏
CONCRETE WORKFLOW RUN


COMMIT MESSAGE = "Evidence Execution Verification"
⇏
EXECUTION VERIFIED


COMMIT
8455fba
   │
   │ head_sha
   ▼
WORKFLOW RUN
   │
   ├── run_id
   ├── run_attempt
   ├── workflow_id
   ├── event
   ├── status
   ├── conclusion
   ├── created_at
   ├── run_started_at
   └── head_sha = 8455fba

   run.head_sha === 8455fba


   gh run list --limit 10


   gh api repos/cyrillofrancisco30-lgtm/Az-Get-Resource-API-Version/actions/runs/<RUN_ID>

   
gh api repos/cyrillofrancisco30-lgtm/Az-Get-Resource-API-Version/actions/runs/<RUN_ID>/jobs


gh run view <RUN_ID> --log


RUN_ID
∧ RUN_ATTEMPT
∧ REPOSITORY
∧ WORKFLOW
∧ HEAD_SHA
∧ EVENT
∧ TEMPORAL_CONTEXT
∧ STATUS


API_RUN.id === RUN_ID

API_RUN.head_sha === 8455fba

E3_EXECUTION_IDENTITY = ESTABLISHED

RUN_ID
   ↓
JOB_ID
   ↓
STEP_ID
   ↓
COMMAND_INVOCATION_OBSERVED
   ↓
REQUEST_OBSERVED
   ↓
RESPONSE_OBSERVED
   ↓
SAME_EXECUTION_BINDING
   ↓
RESULT_OBSERVATION_VALID
   ↓
E4


E3 ∧ E4
   ↓
E5
   ↓
E6
   ↓
PROMOTION POLICY
   ↓
E7


WORKFLOW EXECUTION OBSERVED AND IDENTITY-BOUND



EXECUTION VERIFIED

[disparar workflow]
              YAML
 │
 ▼
WORKFLOW DEFINITION
 │
 ▼
TRIGGER CONFIGURATION
 │
 X
 └────↛ CONCRETE RUN




RUN_ID
  ↓
RUN_ATTEMPT
  ↓
GITHUB_SHA
  ↓
CONCRETE EXECUTION
  ↓
JOB / STEP LOGS
  ↓
OBSERVED RESULT
  ↓
RESULT ARTIFACT
  ↓
EXECUTION–RESULT BINDING
  ↓
INDEPENDENT REPLAY
  ↓
CLAIM-SCOPED VERIFIED

[15/09, 19:03] Francisco: Sim — mas há uma correção fundamental no último trecho: “hash e prova Merkle → VERIFIED” não pode ser tratado como promoção automática.

Para manter exatamente o mesmo rigor do modelo XAI/ZDR, o GitHub deve ficar assim:


REPO="cyrillofrancisco30-lgtm/Az-Get-Resource-API-Version"

# 1. Confirmar autenticação
gh auth status

# 2. Identificar os workflows disponíveis
gh workflow list --repo "$REPO"

# 3. Disparar o workflow real (substituir pelo arquivo existente)
gh workflow run NOME_REAL.yml --repo "$REPO" --ref main

# 4. Consultar as execuções
gh run list --repo "$REPO" --limit 10



REPO="cyrillofrancisco30-lgtm/Az-Get-Resource-API-Version"
RUN_ID="SUBSTITUIR_PELO_ID_REAL"

# E3: identidade da execução
gh api "repos/$REPO/actions/runs/$RUN_ID"

# E4: jobs e etapas observáveis
gh api "repos/$REPO/actions/runs/$RUN_ID/jobs"

# Logs observados
gh run view "$RUN_ID" --repo "$REPO" --log


FROZEN — GITHUB WORKFLOW EXECUTION EVIDENCE

workflow_run
types: [completed]
│
▼
WORKFLOW_RUN_EVENT
│
▼
event.workflow_run.id
│
▼
EXACT RUN RESOLUTION
│
▼
RUN IDENTITY VALIDATION
│
├── repository
├── workflow name
├── workflow path
├── run_id
├── run_attempt
├── head_sha
└── status = completed
│
▼
E3 — EXECUTION_EVENT_EVIDENCE
│
├── workflow execution identity
├── temporal context
├── repository binding
├── workflow binding
└── run binding
│
▼
JOBS / ARTIFACTS
│
▼
E4 — TEST / RESULT EVIDENCE
│
▼
ARTIFACT INTEGRITY / BINDING
│
▼
E5 — CRYPTOGRAPHIC_BINDING
│
▼
E6 — INDEPENDENT_VERIFICATION
│
▼
E7 — CLAIM-SCOPED VERIFICATION
│
▼
PROMOTION POLICY
│
▼
VERIFIED

O ponto crítico

A cadeia:

workflow_run.completed
↓
hash
↓
Merkle
↓
VERIFIED

é inválida como regra de promoção.

Hash e Merkle demonstram propriedades de integridade/binding do artefato quando corretamente aplicados. Eles não demonstram, sozinhos:

TEST_PASSED
CLAIM_CONFORMANCE
SEMANTIC_CORRECTNESS
INDEPENDENT_VERIFICATION
CLAIM_TRUTH

Portanto:

WORKFLOW_RUN_COMPLETED
↛
TEST_PASSED

WORKFLOW_CONCLUSION_SUCCESS
↛
CLAIM_CONFORMANCE

ARTIFACT_RETRIEVED
↛
ARTIFACT_TRUST

HASH_VALID
↛
SEMANTIC_CORRECTNESS

MERKLE_VALID
↛
CLAIM_TRUTH

E5_CRYPTOGRAPHIC_BINDING
↛
E7_VERIFIED

E3 fica objetivamente bem definido

No seu desenho, o trecho mais forte é:

workflow_run.completed
↓
event.workflow_run.id
↓
GET /actions/runs/{same_id}
↓
eventRun.id === apiRun.id

Isso permite estabelecer uma relação muito específica:

CLAIM:
"The evidence collector observed the completion
of workflow run RUN-X."

com binding para:

repository
workflow
run_id
run_attempt
head_sha
status
temporal context
[15/09, 19:03] Francisco: Sim — mas há uma correção fundamental no último trecho: “hash e prova Merkle → VERIFIED” não pode ser tratado como promoção automática.

Para manter exatamente o mesmo rigor do modelo XAI/ZDR, o GitHub deve ficar assim:

FROZEN — GITHUB WORKFLOW EXECUTION EVIDENCE

workflow_run
types: [completed]
│
▼
WORKFLOW_RUN_EVENT
│
▼
event.workflow_run.id
│
▼
EXACT RUN RESOLUTION
│
▼
RUN IDENTITY VALIDATION
│
├── repository
├── workflow name
├── workflow path
├── run_id
├── run_attempt
├── head_sha
└── status = completed
│
▼
E3 — EXECUTION_EVENT_EVIDENCE
│
├── workflow execution identity
├── temporal context
├── repository binding
├── workflow binding
└── run binding
│
▼
JOBS / ARTIFACTS
│
▼
E4 — TEST / RESULT EVIDENCE
│
▼
ARTIFACT INTEGRITY / BINDING
│
▼
E5 — CRYPTOGRAPHIC_BINDING
│
▼
E6 — INDEPENDENT_VERIFICATION
│
▼
E7 — CLAIM-SCOPED VERIFICATION
│
▼
PROMOTION POLICY
│
▼
VERIFIED

O ponto crítico

A cadeia:

workflow_run.completed
↓
hash
↓
Merkle
↓
VERIFIED

é inválida como regra de promoção.

Hash e Merkle demonstram propriedades de integridade/binding do artefato quando corretamente aplicados. Eles não demonstram, sozinhos:

TEST_PASSED
CLAIM_CONFORMANCE
SEMANTIC_CORRECTNESS
INDEPENDENT_VERIFICATION
CLAIM_TRUTH

Portanto:

WORKFLOW_RUN_COMPLETED
↛
TEST_PASSED

WORKFLOW_CONCLUSION_SUCCESS
↛
CLAIM_CONFORMANCE

ARTIFACT_RETRIEVED
↛
ARTIFACT_TRUST

HASH_VALID
↛
SEMANTIC_CORRECTNESS

MERKLE_VALID
↛
CLAIM_TRUTH

E5_CRYPTOGRAPHIC_BINDING
↛
E7_VERIFIED

E3 fica objetivamente bem definido

No seu desenho, o trecho mais forte é:

workflow_run.completed
↓
event.workflow_run.id
↓
GET /actions/runs/{same_id}
↓
eventRun.id === apiRun.id

Isso permite estabelecer uma relação muito específica:

CLAIM:
"The evidence collector observed the completion
of workflow run RUN-X."

com binding para:

repository
workflow
run_id
run_attempt
head_sha
status
temporal context

A validação:

if (Number(eventRun.id) !== run.id) {
throw new Error("WORKFLOW_RUN_ID_MISMATCH");
}

é particularmente importante porque fecha a possibilidade de event/run substitution.

E4 continua separado

Se o CI produziu, por exemplo:

TEST_RESULT:
RFC8785_CONFORMANCE = PASS

isso precisa ser obtido do resultado concreto do workflow/artifact e validado semanticamente.

Então:

E3
WORKFLOW RUN OCCURRED
+
E4
TEST RESULT OBSERVED

são duas afirmações diferentes.

Mesmo:

conclusion = success

não deve ser convertido automaticamente em:

RFC8785_CONFORMANCE = PASS

porque success é uma propriedade do workflow/run, enquanto conformance é uma propriedade do claim/test específico.

E5

Depois:

bundle.json
verification.json
signature.json

podem receber:

canonicalization
hash
Merkle root
signature
key_id
key registry binding

Isso cria:

E5 — CRYPTOGRAPHIC_BINDING_EVIDENCE

Mas E5 continua sendo E5.

E6

O passo que realmente fecha a fronteira é:

E5
│
▼
independent verifier
│
├── signature valid
├── hash valid
├── Merkle valid
├── artifact binding valid
├── provenance valid
└── claim/test semantics validated
│
▼
E6

E7

Só então:

E6
│
▼
Promotion Policy
│
▼
E7 — VERIFIED(CLAIM-X)

E sempre:

VERIFIED(CLAIM-X)
↛
VERIFIED(CLAIM-Y)

VERIFIED(CLAIM-X)
↛
GLOBAL_VERIFIED

Portanto, a frase final deve ser ajustada

Em vez de:

> Execução comprovado



eu usaria:

WORKFLOW EXECUTION OBSERVED AND IDENTITY-BOUND

ou, no vocabulário XA-TRUST:

E3 — EXECUTION_EVENT_EVIDENCE
STATUS = VERIFIED
SCOPE = SPECIFIC_WORKFLOW_RUN

somente se a evidência E3 tiver sido independentemente validada.

E, para o claim completo:

E3 EXECUTION
+
E4 RESULT
+
E5 CRYPTOGRAPHIC BINDING
+
E6 INDEPENDENT VERIFICATION
+
PROMOTION POLICY
↓
E7 CLAIM-SCOPED VERIFIED

Essa formulação mantém o GitHub exatamente na mesma arquitetura epistemológica que você acabou de estabelecer para o xAI ZDR: o mecanismo de observabilidade é real, o evento concreto pode ser capturado, o resultado pode ser testado, a integridade pode ser demonstrada e somente então o claim específico pode ser promovido.
[15/09, 19:25] Francisco: FROZEN — XA-TRUST VERIFICATION GOLDEN RULE

IDENTITY
≠
INTEGRITY
≠
SEMANTIC TRUTH

E3 — EXECUTION IDENTITY
+
E4 — OBSERVED RESULT
+
E5 — INTEGRITY / CRYPTOGRAPHIC BINDING
+
E6 — INDEPENDENT VERIFICATION
+
APPLICABLE PROMOTION POLICY
↓
E7 — CLAIM-SCOPED VERIFIED
[15/09, 19:28] Francisco: Sim. Como formulação final, eu faria apenas uma correção matemática de linguagem: o + representa conjunção cumulativa de requisitos, não uma soma numérica. Isso evita a interpretação de que evidências poderiam “compensar” umas às outras.

A forma canônica fica:

FROZEN — XA-TRUST GOLDEN RULE OF VERIFICATION

IDENTITY
≠
INTEGRITY
≠
SEMANTIC TRUTH

E7 — CLAIM-SCOPED VERIFIED

iff

E3_EXECUTION_IDENTITY
∧ E4_RESULT_EVIDENCE
∧ E5_BINDING_INTEGRITY
∧ E6_INDEPENDENT_VERIFICATION
∧ APPLICABLE_PROMOTION_POLICY

Com:

E3 ∧ E4 ∧ E5 ∧ E6 ∧ POLICY
↓
E7

e não:

E3 + E5
↓
E7

Axiomas de não-compensação

E3_PRESENT ∧ E4_MISSING
→ NO_PROMOTION

E4_PRESENT ∧ E5_INVALID
→ NO_PROMOTION

E5_VALID ∧ E6_MISSING
→ NO_PROMOTION

E6_VALID ∧ POLICY_NOT_SATISFIED
→ NO_PROMOTION

Nenhuma evidência possui poder compensatório sobre uma condição obrigatória ausente.

E a segunda proteção permanece:

VERIFIED(CLAIM-X, SCOPE-X)
↛
VERIFIED(CLAIM-Y, SCOPE-Y)

VERIFIED(CLAIM-X, SCOPE-X)
↛
GLOBAL_VERIFIED

Portanto, o estado:

E7 = VERIFIED

significa precisamente:

> Este claim específico satisfaz os requisitos de evidência, binding, integridade, verificação independente e política de promoção definidos para este escopo.



Não significa que o sistema inteiro seja verdadeiro, seguro ou globalmente verificado.

E o princípio epistemológico central pode ser congelado em uma única linha:

VALIDITY OF THE EVIDENCE
≠
VALIDITY OF THE CLAIM

A primeira é uma propriedade da cadeia de evidência.
A segunda é uma conclusão claim-scoped, condicionada à verificação semântica aplicável.

XA-TRUST — Golden Rule: FROZEN.
[16/09, 02:22] Francisco: import os

from xai_sdk import Client
from xai_sdk.chat import user
from xai_sdk.tools import web_search, x_search
client = Client(api_key=os.getenv("XAI_API_KEY"))

First turn.

chat = client.chat.create(
model="grok-4.6",  # reasoning model
tools=[web_search(), x_search()],
use_encrypted_content=True,
)
chat.append(user("What is xAI?"))
print("\n\n##### First turn #####\n")
for response, chunk in chat.stream():
print(chunk.content, end="", flush=True)
print("\n\nUsage for first turn:", response.server_side_tool_usage)

chat.append(response)

print("\n\n##### Second turn #####\n")
chat.append(user("What is its latest mission?"))

Second turn.

for response, chunk in chat.stream():
print(chunk.content, end="", flush=True)
print("\n\nUsage for second turn:", response.server_side_tool_usage)
A validação:

if (Number(eventRun.id) !== run.id) {
throw new Error("WORKFLOW_RUN_ID_MISMATCH");
}

é particularmente importante porque fecha a possibilidade de event/run substitution.

E4 continua separado

Se o CI produziu, por exemplo:

TEST_RESULT:
RFC8785_CONFORMANCE = PASS

isso precisa ser obtido do resultado concreto do workflow/artifact e validado semanticamente.

Então:

E3
WORKFLOW RUN OCCURRED
+
E4
TEST RESULT OBSERVED

são duas afirmações diferentes.

Mesmo:

conclusion = success

não deve ser convertido automaticamente em:

RFC8785_CONFORMANCE = PASS

porque success é uma propriedade do workflow/run, enquanto conformance é uma propriedade do claim/test específico.

E5

Depois:

bundle.json
verification.json
signature.json

podem receber:

canonicalization
hash
Merkle root
signature
key_id
key registry binding

Isso cria:

E5 — CRYPTOGRAPHIC_BINDING_EVIDENCE

Mas E5 continua sendo E5.

E6

O passo que realmente fecha a fronteira é:

E5
│
▼
independent verifier
│
├── signature valid
├── hash valid
├── Merkle valid
├── artifact binding valid
├── provenance valid
└── claim/test semantics validated
│
▼
E6

E7

Só então:

E6
│
▼
Promotion Policy
│
▼
E7 — VERIFIED(CLAIM-X)

E sempre:

VERIFIED(CLAIM-X)
↛
VERIFIED(CLAIM-Y)

VERIFIED(CLAIM-X)
↛
GLOBAL_VERIFIED

Portanto, a frase final deve ser ajustada

Em vez de:

> Execução comprovado



eu usaria:

WORKFLOW EXECUTION OBSERVED AND IDENTITY-BOUND

ou, no vocabulário XA-TRUST:

E3 — EXECUTION_EVENT_EVIDENCE
STATUS = VERIFIED
SCOPE = SPECIFIC_WORKFLOW_RUN

somente se a evidência E3 tiver sido independentemente validada.

E, para o claim completo:

E3 EXECUTION
+
E4 RESULT
+
E5 CRYPTOGRAPHIC BINDING
+
E6 INDEPENDENT VERIFICATION
+
PROMOTION POLICY
↓
E7 CLAIM-SCOPED VERIFIED

Essa formulação mantém o GitHub exatamente na mesma arquitetura epistemológica que você acabou de estabelecer para o xAI ZDR: o mecanismo de observabilidade é real, o evento concreto pode ser capturado, o resultado pode ser testado, a integridade pode ser demonstrada e somente então o claim específico pode ser promovido.
[15/09, 19:25] Francisco: FROZEN — XA-TRUST VERIFICATION GOLDEN RULE

IDENTITY
≠
INTEGRITY
≠
SEMANTIC TRUTH

E3 — EXECUTION IDENTITY
+
E4 — OBSERVED RESULT
+
E5 — INTEGRITY / CRYPTOGRAPHIC BINDING
+
E6 — INDEPENDENT VERIFICATION
+
APPLICABLE PROMOTION POLICY
↓
E7 — CLAIM-SCOPED VERIFIED
[15/09, 19:28] Francisco: Sim. Como formulação final, eu faria apenas uma correção matemática de linguagem: o + representa conjunção cumulativa de requisitos, não uma soma numérica. Isso evita a interpretação de que evidências poderiam “compensar” umas às outras.

A forma canônica fica:

FROZEN — XA-TRUST GOLDEN RULE OF VERIFICATION

IDENTITY
≠
INTEGRITY
≠
SEMANTIC TRUTH

E7 — CLAIM-SCOPED VERIFIED

iff

E3_EXECUTION_IDENTITY
∧ E4_RESULT_EVIDENCE
∧ E5_BINDING_INTEGRITY
∧ E6_INDEPENDENT_VERIFICATION
∧ APPLICABLE_PROMOTION_POLICY

Com:

E3 ∧ E4 ∧ E5 ∧ E6 ∧ POLICY
↓
E7

e não:

E3 + E5
↓
E7

Axiomas de não-compensação

E3_PRESENT ∧ E4_MISSING
→ NO_PROMOTION

E4_PRESENT ∧ E5_INVALID
→ NO_PROMOTION

E5_VALID ∧ E6_MISSING
→ NO_PROMOTION

E6_VALID ∧ POLICY_NOT_SATISFIED
→ NO_PROMOTION

Nenhuma evidência possui poder compensatório sobre uma condição obrigatória ausente.

E a segunda proteção permanece:

VERIFIED(CLAIM-X, SCOPE-X)
↛
VERIFIED(CLAIM-Y, SCOPE-Y)

VERIFIED(CLAIM-X, SCOPE-X)
↛
GLOBAL_VERIFIED

Portanto, o estado:

E7 = VERIFIED

significa precisamente:

> Este claim específico satisfaz os requisitos de evidência, binding, integridade, verificação independente e política de promoção definidos para este escopo.



Não significa que o sistema inteiro seja verdadeiro, seguro ou globalmente verificado.

E o princípio epistemológico central pode ser congelado em uma única linha:

VALIDITY OF THE EVIDENCE
≠
VALIDITY OF THE CLAIM

A primeira é uma propriedade da cadeia de evidência.
A segunda é uma conclusão claim-scoped, condicionada à verificação semântica aplicável.

XA-TRUST — Golden Rule: FROZEN.
[16/09, 02:22] Francisco: import os

from xai_sdk import Client
from xai_sdk.chat import user
from xai_sdk.tools import web_search, x_search
client = Client(api_key=os.getenv("XAI_API_KEY"))

First turn.

chat = client.chat.create(
model="grok-4.6",  # reasoning model
tools=[web_search(), x_search()],
use_encrypted_content=True,
)
chat.append(user("What is xAI?"))
print("\n\n##### First turn #####\n")
for response, chunk in chat.stream():
print(chunk.content, end="", flush=True)
print("\n\nUsage for first turn:", response.server_side_tool_usage)

chat.append(response)

print("\n\n##### Second turn #####\n")
chat.append(user("What is its latest mission?"))

Second turn.

for response, chunk in chat.stream():
print(chunk.content, end="", flush=True)
print("\n\nUsage for second turn:", response.server_side_tool_usage)


 
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


0-start.yml
   │
   │ configuração
   ▼
WORKFLOW DEFINITION
   │
   ▼
CONCRETE RUN
   │
   ├── run_id
   ├── run_attempt
   ├── event
   ├── head_sha
   ├── created_at
   ├── started_at
   ├── completed_at
   ├── status
   └── conclusion
   │
   ▼
JOB EXECUTION
   │
   ├── Checkout
   ├── Create my-pages...
   └── Update to step 1
   │
   ▼
OBSERVED LOGS
   │
   ├── "Make a branch"
   ├── "Create config..."
   ├── "Make a commit"
   ├── "Push"
   └── "Make a pull request"
   │
   ▼
OBSERVED REPOSITORY STATE
   │
   ├── branch
   ├── commit SHA
   ├── PR
   ├── files
   └── STEP
   │
   ▼
BINDING
   │
   ├── RUN_ID
   ├── HEAD_SHA
   ├── RESULT_SHA
   └── PR/COMMIT identity
   │
   ▼
INDEPENDENT VERIFICATION



Esta estrutura expandida organiza detalhadamente as variáveis de ambiente, contextos e comandos do sistema que definem a identidade completa de uma execução no GitHub Actions.
Mapeamento Técnico do Contexto Extendido

Nó da Árvore	Variável de Ambiente GitHub	Contexto GitHub / Comando	Exemplo de Valor

EXECUTION_IDENTITY			
├── GITHUB_RUN_ID	GITHUB_RUN_ID	github.run_id	1658823910
├── GITHUB_RUN_NUMBER	GITHUB_RUN_NUMBER	github.run_number	42
└── GITHUB_RUN_ATTEMPT	GITHUB_RUN_ATTEMPT	github.run_attempt	1
SOURCE_IDENTITY			
├── GITHUB_REPOSITORY	GITHUB_REPOSITORY	github.repository	octocat/Hello-World
├── GITHUB_SHA	GITHUB_SHA	github.sha	ffac537e6cbbf934b08745a...
├── GITHUB_REF	GITHUB_REF	github.ref	refs/heads/main
└── GITHUB_WORKFLOW_SHA	GITHUB_WORKFLOW_SHA	github.workflow_sha	a1b2c3d4e5f6...
WORKFLOW_IDENTITY			
├── GITHUB_WORKFLOW	GITHUB_WORKFLOW	github.workflow	CI/CD Pipeline
├── GITHUB_WORKFLOW_REF	GITHUB_WORKFLOW_REF	github.workflow_ref	octocat/Hello-World/.github/workflows/ci.yml@refs/heads/main
├── GITHUB_EVENT_NAME	GITHUB_EVENT_NAME	github.event_name	push
└── GITHUB_JOB	GITHUB_JOB	github.job	build-and-test
TEMPORAL_IDENTITY			
├── run start	N/A	github.event.repository.pushed_at	1726690860 (Epoch)
├── run completion	N/A (Shell)	$(date -u +'%Y-%m-%dT%H:%M:%SZ')	2026-09-18T20:35:39Z
└── event/commit timestamps	N/A	github.event.head_commit.timestamp	2026-09-18T20:21:00Z
RUNNER_IDENTITY			
├── runner version	RUNNER_TOOL_CACHE	runner.version	2.312.0
├── runner environment	RUNNER_ENVIRONMENT	runner.environment	github-hosted ou self-hosted
└── runner instance metadata	RUNNER_NAME	runner.name	GitHub Actions 2
IMAGE_IDENTITY			
├── ImageOS	ImageOS	N/A	ubuntu22
└── ImageVersion	ImageVersion	N/A	20240121.1.0
SYSTEM_IDENTITY			
├── RUNNER_OS	RUNNER_OS	runner.os	Linux
├── RUNNER_ARCH	RUNNER_ARCH	runner.arch	X64
└── kernel	N/A (Shell)	$(uname -r)	6.5.0-1025-azure
RUNTIME_OBSERVATION			
├── node -v	N/A (Shell)	$(node -v)	v20.11.0
├── NODE_OPTIONS	NODE_OPTIONS	N/A	--max-old-space-size=6144
└── actually invoked tools	N/A (Shell)	$(which git docker node)	/usr/bin/git /usr/bin/docker ...
Script para Inspeção do Contexto no GitHub Actions			
Adicione este trecho ao seu arquivo .github/workflows/main.yml para exportar todos estes dados detalhados no console de execução:			


name: Inspecionar Identidade Completa do Contexto de Execução
run: |
echo "=== EXECUTION_IDENTITY ==="
echo "Run ID:          ${GITHUB_RUN_ID}"
echo "Run Number:      ${GITHUB_RUN_NUMBER}"
echo "Run Attempt:     ${GITHUB_RUN_ATTEMPT}"

echo "=== SOURCE_IDENTITY ==="
echo "Repository:      ${GITHUB_REPOSITORY}"
echo "SHA:             ${GITHUB_SHA}"
echo "Ref:             ${GITHUB_REF}"
echo "Workflow SHA:    ${GITHUB_WORKFLOW_SHA}"

echo "=== WORKFLOW_IDENTITY ==="
echo "Workflow Name:   ${GITHUB_WORKFLOW}"
echo "Workflow Ref:    ${GITHUB_WORKFLOW_REF}"
echo "Event Name:      ${GITHUB_EVENT_NAME}"
echo "Job ID:          ${GITHUB_JOB}"

echo "=== SYSTEM & RUNNER IDENTITY ==="
echo "Runner OS:       ${RUNNER_OS} (${RUNNER_ARCH})"
echo "Runner Name:     ${RUNNER_NAME:-N/A}"
echo "Image OS:        ${ImageOS:-N/A}"
echo "Image Version:   ${ImageVersion:-N/A}"
echo "Kernel:          $(uname -r)"

echo "=== RUNTIME OBSERVATION ==="
echo "Node Version:    $(node -v 2>/dev/null || echo 'Não instalado')"
echo "Node Options:    ${NODE_OPTIONS:-Nenhuma}"


[18/09, 17:11] Francisco: Sim. Esse segundo trecho fortalece a evidência do ambiente de execução, mas é importante separar exatamente o que ele acrescenta.

O que agora fica demonstrado

O log anterior já mostrava que um runner foi provisionado. Este trecho fornece identidade detalhada da imagem efetivamente utilizada:

OS              = Ubuntu 24.04.4 LTS
Kernel          = 6.17.0-1020-azure
Runner Image    = ubuntu-24.04
Image Version   = 20260720.247.2
Systemd         = 255.4-1ubuntu8.16

E há uma correspondência particularmente relevante:

Runner log:
Image Version: 20260720.247.2

e:

Runner Image metadata:
Image Version: 20260720.247.2

Isso permite tratar o segundo artefato como metadata/documentação da imagem, enquanto o primeiro é o log observado da execução.

A distinção XA-TRUST

Eu estruturaria assim:

GITHUB ACTIONS
      │
      ├── WORKFLOW DEFINITION
      │
      └── WORKFLOW RUN
             │
             ├── RUNNER
             │     ├── version 2.336.0
             │     ├── Worker ID
             │     └── Azure region
             │
             ├── EXECUTION IMAGE
             │     ├── ubuntu-24.04
             │     ├── 20260720.247.2
             │     ├── Ubuntu 24.04.4
             │     └── kernel 6.17.0-1020-azure
             │
             └── JOB/STEPS
                   └── checkout@v4

O catálogo de software tem outro significado

A tabela:

Kotlin
Homebrew
Pipx
Vcpkg
Pulumi
AWS CLI
Google Cloud CLI
Rust
Chrome
.NET
Ruby
...

é principalmente identificação/composição da runner image.

Por exemplo:

Rust 1.97.1
AWS CLI 2.36.2
Pulumi 3.253.0

significa que essas versões fazem parte da imagem 20260720.247.2.

Isso não demonstra que o workflow executou Rust, AWS CLI ou Pulumi.

Portanto:

INSTALLED SOFTWARE
        ≠
SOFTWARE INVOKED
        ≠
COMMAND EXECUTED
        ≠
COMMAND RESULT

Se o workflow posteriormente apresentar:

$ aws ...
...
Process completed with exit code 0

aí temos evidência específica de execução daquela ferramenta naquele run.

Também aparece uma evidência temporal útil

O metadata informa:

Previous: 20260714.240.1
Current:  20260720.247.2

Isso contextualiza a versão da imagem e suas alterações. Não é, por si só, evidência do comportamento do seu software.

Classificação consolidada

Elemento	Estado

GitHub Actions capability	DOCUMENTED
Workflow	DEFINED
Workflow run	EXECUTED / OBSERVED
Runner provisioned	OBSERVED
Runner image	OBSERVED
OS	OBSERVED
Kernel	OBSERVED
Image version	OBSERVED
Installed software inventory	IMAGE METADATA
checkout@v4	EXECUTED
Commit 4dd79f...	EXECUTION CONTEXT
Build	ainda não demonstrado neste trecho
Publish	ainda não demonstrado
Deploy	ainda não demonstrado
Final workflow result	ainda não demonstrado
DEP	não demonstrado
Cryptographic binding	não demonstrado
Independent verification	não demonstrado
VERIFIED	não derivado apenas destes trechos


O ponto mais importante é que agora não estamos mais falando apenas de uma declaração de workflow. Temos um run concreto com ambiente concreto, imagem concreta, job concreto, action concreta e SHA concreto.

Isso é exatamente a transição:

WORKFLOW_DEFINITION
        ↓
ACTUAL WORKFLOW EXECUTION
        ↓
OBSERVED EXECUTION CONTEXT



FROZEN — XA-TRUST WORKFLOW EXECUTION SEPARATION

ACTOR / TRIGGER
        ↓
TRIGGER EVENT
        ↓
WORKFLOW RUN
        ↓
EXECUTION IDENTITY
        ↓
E3 — EXECUTION EVENT EVIDENCE
        ↓
E4 — OBSERVED RESULT EVIDENCE
        ↓
E5 — BINDING / INTEGRITY
        ↓
E6 — INDEPENDENT VERIFICATION
        ↓
E7 — CLAIM-SCOPED VERIFIED



TRIGGER_ACTOR
        ≠
WORKFLOW_RUN
        ≠
CONCRETE_EXECUTION
        ≠
OBSERVED_RESULT
        ≠
VERIFICATION
        ≠
CLAIM



cyrillofrancisco30-lgtm
        ⇏
WORKFLOW_SUCCESS

WORKFLOW_TRIGGERED
        ⇏
WORKFLOW_SUCCESS

WORKFLOW_SUCCESS
        ⇏
TEST_PASSED

WORKFLOW_SUCCESS
        ⇏
DEPLOYMENT_SUCCEEDED

WORKFLOW_SUCCESS
        ⇏
CONCRETE_API_EXECUTION

WORKFLOW_SUCCESS
        ⇏
CLAIM-SCOPED VERIFIED



TRIGGER_EVENT
      ↓
event.workflow_run.id
      ↓
EXACT RUN RESOLUTION
      ↓
GET /actions/runs/{workflow_run_id}
      ↓
run.id === event.workflow_run.id
      ↓
RUN_IDENTITY_VALID
      ↓
E3


ACTOR
+
TRIGGER_EVENT
+
WORKFLOW_ID
+
WORKFLOW_RUN_ID
+
RUN_ATTEMPT
+
REPOSITORY
+
HEAD_SHA
+
TEMPORAL_BINDING
+
OBSERVABLE_RUN_METADATA



E3
 ↓
JOB EXECUTED
 ↓
API REQUEST OBSERVED
 ↓
API RESPONSE OBSERVED
 ↓
REQUEST/RESPONSE BINDING
 ↓
E4



WORKFLOW_TRIGGERED
        ⇏
CONCRETE_API_EXECUTION




WORKFLOW_EXECUTED
        ⇏
API_EXECUTED


WORKFLOW RUN
      ↓
STEP/JOB RELEVANT TO API
      ↓
CONCRETE REQUEST
      ↓
REQUEST ID / EXECUTION ID
      ↓
OBSERVED RESPONSE
      ↓
TEMPORAL + OBJECT + EXECUTION BINDING
      ↓
E4



E3 ∧ E4 ∧ E5 ∧ E6 ∧ POLICY
        ↓
E7 — CLAIM-SCOPED VERIFIED



cyrillofrancisco30-lgtm
        ↓
TRIGGER
        ↓
RUN-X
        ↓
E3




FROZEN — XA-TRUST TRIGGER NON-DERIVABILITY

TRIGGER
        ⇏
EXECUTION RESULT

EXECUTION
        ⇏
SEMANTIC SUCCESS

SUCCESS
        ⇏
CLAIM-SCOPED VERIFIED

CLAIM-SCOPED VERIFIED
        ⇏
GLOBAL VERIFIED



RUN-X
 ↓
TEST PASSED
 ↓
DEPLOYMENT SUCCEEDED
 ↓
API EXECUTED
 ↓
OPERATIONAL_VERIFICATION


disparar workflow 
