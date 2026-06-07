<div align="center">
  
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&pause=1000&color=00FF88&center=true&vCenter=true&width=500&lines=Hey%2C+I'm+Aimen;Security+Infrastructure+Engineer;eBPF+%26+Systems+Security;Open+Source+Tool+Builder" alt="Typing SVG" />
  
  <p>
    <a href="https://github.com/dzdzdzdzdzdz213/beacon-guard"><img src="https://img.shields.io/badge/BeaconGuard-eBPF_Kernel_Guard-00FF88?style=flat-square&logo=linux&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/k8s-runtime-guard"><img src="https://img.shields.io/badge/K8s_Runtime_Guard-eBPF_Container_Security-58A6FF?style=flat-square&logo=kubernetes&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/cloudsweep"><img src="https://img.shields.io/badge/CloudSweep-CSPM_Scanner-FF6B6B?style=flat-square&logo=amazonaws&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/cloudsec-pipeline"><img src="https://img.shields.io/badge/CloudSec_Pipeline-OPA%2FRego-7B2FF7?style=flat-square&logo=openpolicyagent&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/cybersec-journey"><img src="https://img.shields.io/badge/Cybersec_Journey-50_Tools-FF6B6B?style=flat-square&logo=python&logoColor=white" /></a>
    <img src="https://img.shields.io/badge/eBPF-Behavioral_Detection-00FF88?style=flat-square&logo=linux&logoColor=white" />
    <img src="https://img.shields.io/badge/MITRE_ATT%26CK-Mapped-005A9C?style=flat-square&logo=mitre&logoColor=white" />
    <img src="https://komarev.com/ghpvc/?username=dzdzdzdzdzdz213&style=flat-square&color=00FF88" />
  </p>
  
</div>

---

I build **security infrastructure** — kernel-level behavioral detection engines, network security monitors, policy-as-code pipelines, and red team tools. I work across the entire stack: eBPF/C kernel probes, Go middleware, FastAPI backends, and React dashboards.

---

## Flagship Projects

### [BeaconGuard — Behavioral Kernel Guard](https://github.com/dzdzdzdzdzdz213/beacon-guard)

Real-time, signature-free process anomaly detection powered by eBPF. Hooks kernel syscalls, builds per-process behavioral baselines, and kills malicious processes before damage.

```
eBPF hooks         Ring buffer      Go userspace          React dashboard
┌──────────────┐   ┌──────────┐   ┌──────────────────┐   ┌─────────────┐
│ execve       │   │          │   │ Event processor  │   │ Live stats  │
│ openat       │──▶│  Events  │──▶│ Behavioral engine│──▶│ Timeline    │
│ tcp_connect  │   │          │   │ Anomaly detector │   │ Alert feed  │
│ mmap / ptrace│   └──────────┘   │ API (REST + SSE) │   │ Process map │
└──────────────┘                  └──────────────────┘   └─────────────┘
```

- **9 kernel hooks**: execve, openat, clone, exit, tcp_connect, udp_sendmsg, mmap, ptrace
- **10 detection rules**: beaconing (variance analysis), reverse shell ports, DNS tunneling, mass file deletion, sensitive file writes, unexpected binaries, executable mmap, ptrace injection, rapid connections, root execution
- **Two-phase operation**: learning mode builds per-process baselines → enforcement mode detects deviations
- **Low-variance beacon detection**: identifies periodic C2 callbacks by analyzing connection interval variance
- **No signatures**: zero false positives from static rules — purely behavioral anomaly detection
- **Tech stack**: C (eBPF), Go, React, Docker, SSE streaming

---

### [CloudSec Pipeline — GitOps Security Policy Engine](https://github.com/dzdzdzdzdzdz213/cloudsec-pipeline)

Block insecure infrastructure before it reaches production. OPA/Rego policies enforced via GitHub Actions and ArgoCD.

```
Developer PR ──→ GitHub Actions ──→ OPA policy evaluation ──→ Pass? ArgoCD deploys
                                    (Terraform + K8s)          Fail? PR blocked
```

- **10 OPA policies**: 5 AWS (security groups, S3, IAM, encryption, logging) + 5 K8s (pods, resources, RBAC, network, namespaces)
- **17 OPA unit tests** validating every policy rule with secure/insecure examples
- Gatekeeper constraint templates for admission control
- Go CLI tool for local policy validation
- Docker Compose + Kind deployment script

---

### [K8s Runtime Guard — Container Security](https://github.com/dzdzdzdzdzdz213/k8s-runtime-guard)

Container-aware runtime security powered by eBPF. Detects escape attempts, cross-namespace attacks, and suspicious container behavior via kernel hooks correlated with K8s audit logs.

- **9 eBPF hooks**: fork, exec, exit, clone (namespace flags), ptrace, mount, cgroup attach, proc access, release_agent
- **10 detection rules**: container escape, cross-ns ptrace, cgroup release_agent (CVE-2022-0492), privileged namespace creation, shell in container, host /proc access, fork bomb, K8s exec, sensitive mount
- **K8s audit log correlation**: matches kubectl exec/attach events to container processes
- **Two-phase operation**: learning mode builds per-container baselines → enforcement detects deviations
- **Mock mode for development**: runs on any platform with simulated container escape scenarios
- **Tech stack**: C (eBPF), Go (cilium/ebpf + REST API), K8s audit API, Docker

---

### [CloudSweep — CSPM Scanner](https://github.com/dzdzdzdzdzdz213/cloudsweep)

Cloud Security Posture Management scanner for AWS. 50+ checks across 9 services with rich reporting in table, JSON, and HTML format.

- **51 security checks**: S3 (8), EC2 (10), IAM (8), KMS (4), CloudTrail (5), RDS (5), Lambda (4), VPC (4), GuardDuty (3)
- **Severity-graded findings**: critical → high → medium → low with remediation guidance
- **HTML reports**: standalone dark-themed report with severity-coded tables
- **Config-driven**: YAML config for regions, services, and thresholds
- **Tech stack**: Python, boto3, Rich (terminal), HTML/JSON reporting

---

### [ShieldWall — Network Security Monitor](https://github.com/dzdzdzdzdzdz213/cybersec-journey/tree/master/shieldwall)

Production-ready network IDS with real-time traffic capture, plugin detection engine, MITRE ATT&CK mapping, and live dashboard.

- 8 detection plugins (port scan, SQLi, DNS tunneling, brute force) with hot-reload
- 40+ MITRE ATT&CK technique mappings per alert
- Multiple output sinks: SQLite, Elasticsearch, Syslog, Webhook, Kafka
- Docker Compose deployment with ES + Kibana + Redis

---

### [Cybersec Journey — 50 Security Tools](https://github.com/dzdzdzdzdzdz213/cybersec-journey)

Monorepo of 50 independently-runnable tools across 7 security domains:

| Domain | Languages | Highlight |
|--------|-----------|-----------|
| **Network Security** | Python, C | Packet sniffer, IDS, DNS tunnel, honeypot |
| **Cryptography** | Python | Steganography, ZK proofs, lattice crypto |
| **Digital Forensics** | Python, ASM | Disk imager, file carver, memory analysis |
| **Red Teaming** | Python, PS | C2 framework, payload generation, lateral movement |
| **Web Security** | Python, JS | SQLi/XSS scanner, JWT inspector, CSRF tester |
| **OSINT** | Python | Domain fingerprinting, social mapper, WHOIS |
| **Malware Analysis** | Python, ASM | YARA scanner, shellcode analyzer, behavioral graph |

---

## Toolchain

```
Kernel        C · eBPF · libbpf
Systems       Go · Rust · Assembly (x86/x64)
Backend       Python · FastAPI · Flask · Node.js
Frontend      React · Recharts · SSE · WebSocket
Infra         Docker · Kubernetes · ArgoCD · Terraform · OPA/Gatekeeper
Storage       SQLite · PostgreSQL · Elasticsearch · Redis
Security      Network analysis · Cryptography · Forensics · Malware · OSINT
```

---

## GitHub

<div align="center">
  
  <a href="https://github.com/dzdzdzdzdzdz213">
    <img height="160em" src="https://github-readme-stats.vercel.app/api?username=dzdzdzdzdzdz213&show_icons=true&theme=dark&hide_border=true&include_all_commits=true&count_private=true&bg_color=0D1117" />
    <img height="160em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=dzdzdzdzdzdz213&layout=compact&theme=dark&hide_border=true&langs_count=8&bg_color=0D1117" />
  </a>
  
  <br />
  
  <a href="https://github.com/dzdzdzdzdzdz213/beacon-guard">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dzdzdzdzdzdz213&repo=beacon-guard&theme=dark&hide_border=true&bg_color=0D1117&description_lines_count=1" />
  </a>
  <a href="https://github.com/dzdzdzdzdzdz213/k8s-runtime-guard">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dzdzdzdzdzdz213&repo=k8s-runtime-guard&theme=dark&hide_border=true&bg_color=0D1117&description_lines_count=1" />
  </a>
  <a href="https://github.com/dzdzdzdzdzdz213/cloudsweep">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=dzdzdzdzdzdz213&repo=cloudsweep&theme=dark&hide_border=true&bg_color=0D1117&description_lines_count=1" />
  </a>
  
</div>

---

<div align="center">
  
  *Security infrastructure engineer. Building tools that make networks safer.*

  <a href="mailto:aimenmamache0@gmail.com"><img src="https://img.shields.io/badge/Email-aimenmamache0%40gmail.com-00FF88?style=flat-square&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/dzdzdzdzdzdz213"><img src="https://img.shields.io/badge/GitHub-dzdzdzdzdzdz213-00FF88?style=flat-square&logo=github&logoColor=white" /></a>
  <img src="https://img.shields.io/badge/Open_to-Security_Engineering_Roles-00FF88?style=flat-square" />
  
</div>
