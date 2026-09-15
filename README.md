# Overview 

This script retrieves the latest and current API versions of the Azure resources deployed in a specified Azure Subscription. 
The script uses Azure PowerShell and Azure DevOps REST APIs to perform the following steps:

- Get the list of repositories under the provided Azure DevOps (AzDO) project and clone/download them locally.
- Search for all files containing "deploy" or "template" in their names and extract the resource type and API version information from each file's JSON content.
- Retrieve the latest 3 API versions for each resource type in the current subscription and compare them to the current API version retrieved from the previous step.
- Lastly, export the results to a CSV file.

# Prerequisites

Before running the script, the following prerequisites must be met:

1. Azure PowerShell module must be installed on the machine where the script will be executed.
2. The Azure DevOps Personal Access Token (PAT) must be obtained and provided as an input parameter to the script. The PAT must have the necessary permissions to access the AzDO project and repositories.
3. The script must be executed on a machine where Git is installed.

# Inputs

The script initializes the following variables:

- $orgUrl: The URL of the Azure DevOps organization.
- $pat: The Personal Access Token (PAT) used for authentication.
- $projectName: The name of the Azure DevOps project.
- $outputFolder: The path to the output folder where the script clones the Azure DevOps project repositories.
- $outputFile: The path to the output file where the script writes the extracted type and apiVersion from each file's JSON content.
- $outputFileAPI: The path to the output file where the script removes whitespaces after the APIVersion.
- $outputFileAPITmp: The path to the temporary output file where the script writes the extracted type and apiVersion from each file's JSON content to remove duplicates.
- $outputFileCSV: The path to the output CSV file where the script exports the results.

# Usage

The script can be either ran manually or via Azure DevOps Pipelines or GitHub Workflows.

1. To run using PowerShell manually, just run the below command:
```
.\Get-AzResourceAPIVersions.ps1 -pat <Azure DevOps PAT> -outputFileCSV <Output CSV file path>
```
  Make sure to replace <Azure DevOps PAT> with the Azure DevOps Personal Access Token and <Output CSV file path> with the path to the output CSV file.
2. To run using Azure DevOps Pipelines, you can use the [azure-pipelines.yml](./azure-pipelines.yml) file as a reference and modify the variables wherever required. 
  
# Outputs
  
The script generates the following output:

- Console output: The script outputs the latest 3 API versions for each resource type and the status of the current API version (outdated, latest, or unable to determine) to the console.
- CSV file: The script exports the results to a CSV file containing the following columns:
  1. ResourceType: The Azure resource type.
  2. LatestApiVersion: The latest 3 API versions for the resource type.
  3. CurrentApiVersion: The current API version for the resource type.
  4. Status: The status of the current API version (outdated, latest, or unable to determine).  
  
# Flow Chart

  ![Az Resource API Version](./Az_Resource_API_version.png)
  
  
  
FROZEN — XA ZDR EVIDENCE BOUNDARY

1. Princípio Fundamental

A existência de documentação, configuração, contexto de execução ou atributo de resposta relacionado a Zero Data Retention (ZDR) NÃO constitui, por si só,.  prova de retenção zero, exclusão de conteúdo, conformidade global ou VERIFIED.

A cadeia de confiança deve preservar a distinção:

ZDR_DOCUMENTATION
        ≠
ZDR_CONFIGURATION
        ≠
ZDR_EXECUTION_CONTEXT
        ≠
ZDR_TEST_RESULT
        ≠
ZDR_CONTENT_RETENTION_EVIDENCE
        ≠
ZDR_CONTENT_DELETION_PROOF
        ≠
CRYPTOGRAPHIC_PROOF
        ≠
INDEPENDENT_VERIFICATION
        ≠
CLAIM-SCOPED VERIFIED
        ≠
GLOBAL VERIFIED

---

2. Escopo

Os seguintes domínios são independentes:

CLAIM_SCOPE
     ≠
SERVICE_SCOPE
     ≠
TEAM_SCOPE
     ≠
REQUEST_SCOPE
     ≠
RESPONSE_SCOPE
     ≠
EXECUTION_SCOPE

Consequentemente:

TEAM ZDR ENABLED
        ↓
contextualizes
        ↓
REQUEST-X
        ↓
RESPONSE-X
        ↓
x-zero-data-retention = "true"

não autoriza a conclusão:

ZDR_GLOBAL_VERIFIED

---

3. Classificação XA-TRUST

Artefato| Classificação| Escopo
Security FAQ| "SOURCE_ARTIFACT"| provider/service
ZDR documentation| "POLICY_EVIDENCE"| policy
Team ZDR Active| "CONFIGURATION_EVIDENCE"| team
API Request| "REQUEST_ARTIFACT"| request
Concrete execution| "E3 EXECUTION_EVENT_EVIDENCE"| execution
API Response| "RESPONSE_ARTIFACT"| request/response
"x-zero-data-retention=true"| "EXECUTION_CONTEXT_EVIDENCE"| request
Header assertion| "TEST_ASSERTION"| claim/test
Observed / Expected / Pass| "E4 TEST_RESULT_EVIDENCE"| claim/test
Hash/signature/binding| "E5 CRYPTOGRAPHIC_BINDING_EVIDENCE"| artifact/binding
Independent verifier| "E6 INDEPENDENT_VERIFICATION_EVENT"| verification
Verification result| "E7 VERIFICATION_RESULT"| claim
Promotion decision| "PROMOTION_DECISION"| claim/policy
Global promotion| "GLOBAL_CLAIM_VERIFIED"| explicitly defined global claim

---

4. E3 — Execution Boundary

REQUEST-X
   │
   ├── request identity
   ├── timestamp
   ├── team
   ├── principal
   ├── operation
   └── execution identity
          │
          ▼
E3 — EXECUTION_EVENT_EVIDENCE

O atributo:

x-zero-data-retention=true

NÃO é E3 isoladamente.

Ele é um atributo observado no "RESPONSE_ARTIFACT" que pode fornecer contexto para uma claim de execução.

Portanto:i

E3 EXECUTION9
        ≠
RESPONSE HEADER

---

i5. E4 — Resultado

A avaliação do atributo deve ser explicitamente definida:

ASSERTION:
x-zero-data-retention == "true"

OBSERVED:
true

EXPECTED:o
true

RESULT:
PASS

Isso produz:

E4 — TEST_RESULT_EVIDENCE

Mas:

PASS

não significa automaticamente:

ZDR_CONTENT_DELETION_PROVED

nem:

GLOBAL_ZDR_COMPLIANCE

---

6. E5 — Binding e Integridade

Quando aplicável, deve ser estabelecida a relação:

E3
 │
 └── workflow/request/execution binding
             ↓
       RESPONSE-X
             │
             └── result/artifact binding
                         ↓
                         E4
                         ↓
                         E5

E5 pode demonstrar, conforme o mecanismo efetivamente validado:

artifact integrity
+
canonical representation
+
hash validity
+
signature validity
+
identity binding
+
temporal binding
+
request/response binding

Nenhum desses elementos, isoladamente, demonstra a verdade semântica da claim.

CRYPTOGRAPHIC_VALIDITY
        ≠
CLAIM_TRUTH

---

7. E6 — Verificação Independente

E6 deve representar uma operação de verificação independente do objeto originalmente produzido:

E3 + E4 + E5
        │
        ▼
E6 — INDEPENDENT_VERIFICATION_EVENT

A existência de:

FAQ
+
ZDR configuration
+
response header

não constitui E6.

---

8. E7 — Claim-Scoped Verification

Somente após satisfazer os requisitos definidos para a claim:

SufficientEvidence(CLAIM)
∧ ValidBinding(CLAIM)
∧ IntegrityValid(CLAIM)
∧ ProvenanceComplete(CLAIM)
∧ IndependentVerification(CLAIM)
∧ PromotionPolicySatisfied(CLAIM)

pode ocorrer:

E7 — CLAIM-SCOPED VERIFIED

Exemplo válido:

CLAIM-001:

"REQUEST-X received a response reporting
x-zero-data-retention = true."

        ↓

CLAIM-001 = VERIFIED

A conclusão permanece limitada ao escopo definido da claim.

---

9. Proibições Normativas

São proibidas as seguintes inferências:

ZDR_DOCUMENTATION
        ↛ VERIFIED

ZDR_CONFIGURATION
        ↛ VERIFIED

x-zero-data-retention=true
        ↛ CONTENT_DELETED

x-zero-data-retention=true
        ↛ CRYPTOGRAPHIC_PROOF

TEST_PASS
        ↛ GLOBAL_ZDR_COMPLIANCE

E7(CLAIM-001)
        ↛
E7(XAI_ZDR_GLOBAL)

LOCAL_VERIFIED
        ↛
GLOBAL_VERIFIED

---

10. Cadeia Canônica

ZDR_DOCUMENTATION
        │
        ▼
ZDR_CONFIGURATION
        │
        │ contextual scope
        ▼
REQUEST-X
        │
        ▼
E3 — EXECUTION_EVENT_EVIDENCE
        │
        ▼
RESPONSE-X
        │
        └── x-zero-data-retention=true
                    │
                    ▼
          EXECUTION_CONTEXT_EVIDENCE
                    │
                    ▼
          E4 — TEST_RESULT_EVIDENCE
                    │
                    ▼
          E5 — CRYPTOGRAPHIC_BINDING
                    │
                    ▼
          E6 — INDEPENDENT_VERIFICATION
                    │
                    ▼
          E7 — CLAIM-SCOPED VERIFIED

---

11. Fronteira de Conteúdo

Particularmente:

ZDR_HEADER_VERIFIED
        ≠
ZDR_CONTENT_RETENTION_VERIFIED
        ≠
ZDR_CONTENT_DELETION_VERIFIED

A demonstração de que uma resposta reportou:

x-zero-data-retention=true

não demonstra, sem evidência adicional específica:

- que nenhum conteúdo foi persistido;
- que nenhum conteúdo foi armazenado temporariamente;
- que nenhum conteúdo foi registrado em outra camada;
- que conteúdo previamente existente foi eliminado;
- que todos os requests da equipe receberam o mesmo tratamento;
- que todos os serviços/subsistemas obedeceram à mesma política;
- que existe conformidade global com ZDR.

Cada uma dessas proposições constitui uma claim própria e requer sua própria evidência, binding e verificação.

---

12. Regra Global

A promoção:

E7_LOCAL_VERIFIED
        ↓
GLOBAL_CLAIM_VERIFIED

é PROIBIDA por implicação.

A promoção global somente pode ocorrer mediante:

GLOBAL_SCOPE_DEFINITION
+
GLOBAL_AGGREGATION_POLICY
+
REQUIRED_LOCAL_CLAIMS
+
AGGREGATION_EVIDENCE
+
GLOBAL_BINDING_VALIDATION
+
INDEPENDENT_GLOBAL_RE-EVALUATION

produzindo:

GLOBAL_CLAIM_VERIFIED

somente para a claim global explicitamente definida.

---

13. Invariante XA-TRUST

A seguinte igualdade deve permanecer invariável:

x-zero-data-retention=true
        ≠
ZDR globally proven

E:

EXECUTION
        ≠
RESULT
        ≠
CRYPTOGRAPHIC VALIDITY
        ≠
INDEPENDENT VERIFICATION
        ≠
CLAIM TRUTH
        ≠
GLOBAL PROMOTION

STATUS

FROZEN

"XA ZDR EVIDENCE BOUNDARY" constitui uma fronteira de confiança do XA-TRUST para impedir a transformação indevida de documentação, configuraç9ão ou metadados de execução em prova de retenção zero, exclusão de conteúdo, conformidade global ou VERIFIED.


