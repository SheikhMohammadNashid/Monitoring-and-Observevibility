The traditional "Three Pillars of Observability" are **Metrics, Logs, and Traces**. However, modern DevOps has evolved to explicitly include **Events and Changes** as a critical extension. Together, they are often referred to as the **MELT** framework (or MELT+Changes).

An interview-ready way to explain these pillars is by matching each one to the specific question it answers during an incident:

### 1. Metrics $\rightarrow$ _"Is there a problem?"_

Metrics are numeric, time-series data aggregated over time (e.g., CPU utilization, memory usage, request counts, or error rates).

- **DevOps Value:** Because they are mathematically lightweight, metrics are perfect for real-time dashboards and triggering automated alerts when thresholds are breached.
    

### 2. Traces $\rightarrow$ _"Where is the problem?"_

Traces track the lifecycle of a single request as it travels through a distributed system or microservices network.

- **DevOps Value:** A trace map shows exactly which specific microservice, API, or database dependency is bottlenecking the request or dropping the ball.
    

### 3. Logs $\rightarrow$ _"Why is it happening?"_

Logs are immutable, timestamped text or JSON records of discrete system code executions (e.g., stack traces, database exceptions).

- **DevOps Value:** Once a trace tells you _where_ the failure is, logs provide the context to show you the exact error string and line of code that triggered it.
    

### 4. Events & Changes $\rightarrow$ _"What caused the problem?"_

Events are structured records of discrete, high-impact occurrences in the ecosystem—most notably, **Changes** (e.g., a new CI/CD code deployment, an infrastructure auto-scaling event, or a feature-flag toggle).

- **DevOps Value:** Over 80% of production outages are triggered by a recent change. Corrolling the timeline of a metric spike directly against a "Deployment Event" gives engineers instant root-cause correlation.
    

> **Interview Tip:** _"While the three traditional pillars—Metrics, Logs, and Traces—help us identify and isolate failures, adding **Events and Changes** completes the picture. It allows us to correlate system degradation directly with engineering actions, leading to the ultimate goal of DevOps: lowering the Mean Time to Resolution (MTTR)."_