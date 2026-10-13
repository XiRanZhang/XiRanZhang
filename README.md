### Hi there 👋

I'm **XiRanZhang** (张曦冉), a backend engineer at **Xiaomi** with 4 years in database infrastructure — MySQL at scale, and stateful databases on Kubernetes.

I'm currently writing an open book: **[有状态工作负载在 Kubernetes 上的调度与运维](https://xiranzhang.github.io/book/)** (Stateful Workloads on Kubernetes: Scheduling & Operations). It's about why Pod-level control can't express quorum, database roles, and membership invariants — and what to actually do about it.

M.S. in Computer Science from Huazhong University of Science and Technology (HUST), B.S. from Wuhan University of Technology.

---

#### What I Do

- **MySQL at Scale** — Building and maintaining the platform behind a large MySQL fleet spanning multiple data centers. Deep source-level expertise in [gh-ost](https://github.com/github/gh-ost) (online schema migration) and [Orchestrator](https://github.com/openark/orchestrator) (HA & replication management).

- **Stateful MySQL on Kubernetes** — Core developer of a stateful MySQL Operator built on [KubeBlocks](https://github.com/apecloud/kubeblocks). I own backup verification/replay, data-carrying horizontal scaling, and online bidirectional migration between bare metal and containers. Scaling a stateful instance means keeping data intact across PVC binding, replica sync, and topology change — the real difficulty is making that sequence ordered and idempotent when controllers update concurrently.

- **Unified SQL Execution Layer** — Designed and built from zero the single execution gateway for every platform SQL change: audit → approval → execute → callback → auto-rollback. Rebuilt the connection pool after a lock-contention diagnosis (network I/O held inside locks, plus a mutex on the hot path), cutting request latency by orders of magnitude under concurrent load.

- **Database AI Access Layer (MCP)** — Exposed the database platform as a suite of standardized agent tools (query, audit, ticketing, slow-query diagnosis, instance management), with multiple concurrent auth modes, tool-level isolation between regular users and DBAs, and guardrails that let an LLM open a SQL change without letting it push one through unsupervised.

- **Database Control Plane (DBaaS)** — SQL change ticketing with sharding-aware routing and AST-based rule grading; multi-region backup across major MySQL versions; the management plane for Xiaomi's sharding middleware Gaea (cluster/node management, failover, hot config reload, online migration off HAProxy); and a `DBService` engine abstraction that reduces onboarding a new engine to a fraction of the original work across MySQL / PostgreSQL / OceanBase.

#### Open Source & Publications

- **[goInception #718](https://github.com/hanchuanchuan/goInception/pull/718)** — Fixed a pipe deadlock in the gh-ost executor: an inaccurate InnoDB row estimate overflows the progress counter, the reader exits, and the pipe blocks. In production this symptom hung migrations for over an hour. Three lines of code — the work was the diagnosis. *(PR open, awaiting review.)*

- **Building on open source** — My work with **[KubeBlocks](https://github.com/apecloud/kubeblocks)** (the stateful MySQL Operator), **[Gaea](https://github.com/XiaoMi/Gaea)** (its management plane) and **[Soar](https://github.com/XiaoMi/soar)** (the audit engine) is against Xiaomi's internal codebases, so it doesn't appear in my public commit history — the public repos are downstream mirrors.

- **CCF-B publication** — [Fault-Tolerating Edge Computing with Server Redundancy Based on a Variant of Group Degree Centrality](https://www.researchgate.net/publication/347461271_Fault-Tolerating_Edge_Computing_with_Server_Redundancy_Based_on_a_Variant_of_Group_Degree_Centrality) (IEEE SCC 2020)

#### Interested In

Quorum-aware scheduling for stateful workloads · Kubernetes operators that respect database protocol semantics · AI agents that can operate databases without being able to break them.

---

📖 [Book](https://xiranzhang.github.io/book/) · ✍️ [All writing](https://xiranzhang.github.io/) · 💬 [Technical discussions](https://github.com/XiRanZhang/XiRanZhang.github.io/issues)
