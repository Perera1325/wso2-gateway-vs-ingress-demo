\# WSO2 Kubernetes Gateway vs Ingress NGINX



A hands-on security and governance comparison between:



\- Ingress NGINX (Annotation-based)

\- WSO2 Kubernetes Gateway (Gateway API-based)



\## Objective



Demonstrate:



\- Annotation misconfiguration risks

\- Snippet security exposure

\- Strong typing validation

\- API governance enforcement

\- Zero-downtime updates



\## Status



🚧 Day 1 – Foundation Setup



\## Snippet Injection Attempt (Blocked)



The controller rejected the configuration-snippet annotation:



"Snippet directives are disabled by the Ingress administrator."



This demonstrates:



\- Snippet-based extensibility created significant security risks.

\- Modern Ingress controllers disable this feature by default.

\- Enabling it requires cluster-wide administrative override.

\- Annotation-based extensibility led to architectural hardening measures.



This supports the argument that annotations became technical debt.







\## Day 4 – Structured Validation Comparison



Demonstrated how Gateway API provides structured status conditions

(ResolvedRefs, BackendNotFound) when backend services are invalid,

compared to Ingress which primarily returns 502 without rich resource-level feedback.

