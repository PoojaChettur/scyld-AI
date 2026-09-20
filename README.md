# ScyldAI — Sentinel-Node

**An AI-Powered, Self-Healing Server Monitoring Agent**
*YESIST12 · IEngage Track · SDG 9 — Industry, Innovation and Infrastructure*
*Team: AFFINITY*

> *"Don't just monitor servers — keep them alive."*

---

## 📌 The Problem

> *"Servers don't crash at noon — they collapse at 3 AM, when no one's watching. And by the time alerts scream, the damage is already done."*

Modern server monitoring tools (Datadog, Prometheus, CloudWatch) act as **reactive smoke detectors** — they raise alerts only after a crash or severe anomaly has already occurred. This leads to:

- **Memory leaks** that silently consume RAM until the system collapses
- **Zombie processes** clogging resources and blocking new workloads
- **Resource overloads** where one greedy service starves others
- **Human cost** — engineers woken at 3 AM, manual fixes taking 15–60 minutes, downtime translating into thousands of dollars lost

---

## 💡 The Solution: Sentinel-Node

**Sentinel-Node** is like an **immune system for cloud servers**. Instead of waiting for failures and waking engineers at 3 AM, it embeds intelligence directly inside the Linux kernel.

- Uses **eBPF** to monitor system calls and resource usage in real time, spotting anomalies (memory leaks, zombie processes, CPU overloads) within **milliseconds** — before they cause downtime
- A **Python-based AI model** classifies risk severity and triggers **micro-recoveries** via **Docker/Kubernetes** integration
- Faulty containers are restarted, caches flushed, or resource limits applied — **all without human intervention**
- Every fix is logged into a **feedback loop**, letting the AI learn and improve continuously

In essence, Sentinel-Node combines **kernel-level speed, AI intelligence, and container resilience** to deliver proactive, precise, self-learning healing.

---

## 🏗️ Architecture

```
Application Layer (Docker/Kubernetes)
   Payment · Auth · Database · Frontend · Cache services
        │  syscalls & metrics
        ▼
eBPF Probe Layer (Linux Kernel — Ring 0)
   Syscall Monitor · Resource Tracer · Process Watcher · Network Probe
        │  telemetry stream
        ▼
AI / ML Engine
   LSTM Detector (anomaly probability)
     → Decision Engine (Random Forest: severity → action)
     → Healing Orchestrator (K8s/OS API micro-recovery)
     → Feedback Loop (RL retraining — learns & improves)
        │
        ├──► Self-Healing Actions
        │      Restart faulty container · Clear stuck cache
        │      Reallocate CPU/RAM · Kill zombie processes
        │      Reroute traffic · Spin up replacement pod
        │      Isolate infected node · Alert human (Level 3 only)
        │
        └──► Observability Dashboard
               Grafana/custom UI · Real-time incident logs
               Healing history · MTTR metrics
```

> eBPF operates at Linux kernel Ring 0 — below Docker and Kubernetes — invisible to existing monitoring tools.

---

## 🧱 Tech Stack

- **Kernel-level monitoring:** eBPF
- **AI/ML:** Python — LSTM (time-series anomaly detection), Random Forest (severity/decision engine), reinforcement learning (feedback loop)
- **Orchestration:** Docker / Kubernetes API
- **Observability:** Grafana / custom dashboard

---

## 📊 Impact (Pre- vs Post-Optimization)

| Metric | Pre-Optimization | Post-Optimization |
|---|---|---|
| CPU Utilization (%) | ~72% | ~57% |
| Memory Utilization (%) | ~65% | ~52% |
| Prediction Accuracy (%) | — | ~92% |
| Anomaly Detection Accuracy (%) | — | ~96% |
| MTTR (minutes) | ~16 | ~8 |
| Availability (%) | ~95% | ~99% |
| MTBF (hours) | — | ~187 |

Compared to traditional tools, Sentinel-Node significantly reduces detection latency, MTTR, and downtime per incident.

---

## ✅ Advantages

- **Proactive detection** — catches anomalies before failure
- **Kernel-level speed** — millisecond response via eBPF
- **Micro-recovery** — fixes only the faulty part, not the whole system
- **Self-learning loop** — improves with every healing action
- **High demo/business appeal** — strong "wow" factor and cost savings

## ⚠️ Limitations

- **Complex kernel integration** — requires deep expertise, risk of instability
- **Limited healing scope** — can't fix deeper application bugs
- **Resource overhead** — monitoring itself consumes CPU/memory
- **AI training challenges** — risk of false positives/negatives
- **Enterprise adoption barriers** — trust and compliance concerns

---

## 🎯 Conclusion

Sentinel-Node acts as the immune system for cloud servers — detecting anomalies proactively, performing micro-recovery at kernel-level speed, and learning continuously through an AI feedback loop. It delivers strong business impact: cost savings, reliability, and future-ready AIOps potential.

---

## 👥 Team AFFINITY

| Name | Role |
|---|---|
| Pooja Chettur S | Team Leader |
| Rakshita Pradhan | Team Member |
| Kowsalya M | Team Member |
| Sujitha J | Team Member |

---

## 📚 References

- FedMon: Federated eBPF Monitoring for Distributed Anomaly Detection in Multi-Cluster Cloud Environments — arXiv (Oct 2025)
- eBPF Research Papers, curated by pchaigno (2025–2026)
- An Anomaly Detection Approach by AIML in IP Networks with eBPF-Based Telemetry — IEEE Xplore (2025)
- AI-Enhanced Runtime Security for Kubernetes: Real-time Threat Detection with eBPF Telemetry and Ensemble Learning — Asian Journal of Research in Computer Science (2025)

