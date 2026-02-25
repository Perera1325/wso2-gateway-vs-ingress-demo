\# Day 5 – Weighted Routing \& Canary Deployment



\## Scenario



Deployed two versions of an application:



\- demo-service (v1)

\- demo-service-v2 (v2)



Configured HTTPRoute with weighted backendRefs:



\- v1 → 80%

\- v2 → 20%



---



\## Gateway API Behavior



Traffic responses showed mixed output:



Hello from Ingress NGINX  

Hello from Gateway V2 🚀  



This confirms:



\- Native weighted routing support

\- No annotations required

\- Strongly typed configuration

\- Portable across implementations



---



\## Ingress Comparison



Weighted routing in NGINX Ingress requires:



nginx.ingress.kubernetes.io/canary: "true"

nginx.ingress.kubernetes.io/canary-weight: "20"



Limitations:



\- Controller-specific

\- Annotation-based

\- Not portable

\- Harder to validate



---



\## Architectural Advantage



Gateway API enables production strategies:



\- Canary deployment

\- Progressive rollout

\- Blue/Green migration

\- Traffic shifting without restarts



This demonstrates a structural advantage over Ingress.

