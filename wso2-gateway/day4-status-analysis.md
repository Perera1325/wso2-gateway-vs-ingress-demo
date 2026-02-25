\# Day 4 – Structured Status Validation (Gateway API vs Ingress)



\## Scenario: Invalid Backend Reference



We intentionally referenced a non-existent service:



backendRefs:

&nbsp; - name: billing-v2



---



\## Gateway API Behavior



Result:



\- Accepted: True

\- ResolvedRefs: False

\- Reason: BackendNotFound

\- Message: service demo/billing-v2 not found



Traffic Response:

\- HTTP 500 returned from data plane



Key Observation:

Gateway API exposes structured status conditions:

\- Accepted

\- Programmed

\- ResolvedRefs



This enables deterministic debugging.



---



\## Ingress Behavior



When referencing a non-existent backend in Ingress:



\- Traffic returns 502

\- No structured condition like ResolvedRefs

\- No explicit BackendNotFound reason



Ingress relies primarily on controller logs rather than resource status.



---



\## Architectural Conclusion



Gateway API separates:



\- Resource acceptance

\- Data plane programming

\- Reference resolution



This improves:



\- Debuggability

\- Operational visibility

\- Multi-team cluster safety

