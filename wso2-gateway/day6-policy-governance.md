\# Day 6 – Policy \& Governance (Rate Limiting)



\## Scenario



Attached a BackendTrafficPolicy to HTTPRoute:



\- Limit: 5 requests per minute



\## Gateway API Behavior



After exceeding 5 requests:



HTTP/1.1 429 Too Many Requests  

x-ratelimit-limit: 5  

x-ratelimit-remaining: 0  



Policy was:



\- Strongly typed

\- Attached via targetRefs

\- Enforced without modifying application code



\## Observations



\- No annotations used

\- No controller-specific configuration

\- Clear status conditions

\- Deterministic enforcement



\## Ingress Comparison



Ingress rate limiting requires annotations:



nginx.ingress.kubernetes.io/limit-rps



Limitations:



\- String-based configuration

\- Controller-specific

\- Harder to validate and govern



\## Architectural Conclusion



Gateway API enables first-class governance:



\- Policy attachment model

\- Clean separation between routing and enforcement

\- Enterprise-ready traffic control

