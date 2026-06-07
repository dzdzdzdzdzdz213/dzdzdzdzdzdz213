<div align="center">
  
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&pause=1000&color=00FF00&center=true&vCenter=true&width=500&lines=Hey%2C+I'm+Aimen;Security+Engineer;Tool+Builder;Network+Defender" alt="Typing SVG" />
  
  <p>
    <a href="https://github.com/dzdzdzdzdzdz213/beacon-guard"><img src="https://img.shields.io/badge/BeaconGuard-eBPF-FF6B6B?style=flat-square&logo=linux&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/cloudsec-pipeline"><img src="https://img.shields.io/badge/CloudSec_Pipeline-OPA%2FRego-7B2FF7?style=flat-square&logo=openpolicyagent&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/cybersec-journey"><img src="https://img.shields.io/badge/50_Cybersec_Tools-FF6B6B?style=flat-square&logo=python&logoColor=white" /></a>
    <a href="https://github.com/dzdzdzdzdzdz213/cybersec-journey/tree/master/shieldwall"><img src="https://img.shields.io/badge/ShieldWall-IDS-00ADD8?style=flat-square&logo=fastapi&logoColor=white" /></a>
    <img src="https://img.shields.io/badge/eBPF-Behavioral-00FF88?style=flat-square&logo=linux&logoColor=white" />
    <img src="https://img.shields.io/badge/MITRE_ATT%26CK-Mapped-005A9C?style=flat-square&logo=mitre&logoColor=white" />
    <img src="https://komarev.com/ghpvc/?username=dzdzdzdzdzdz213&style=flat-square&color=00FF00" />
  </p>
  
</div>

---

I build **cybersecurity infrastructure** — kernel-level behavioral guards, network monitors, policy engines, detection systems, and red team tools. I work from eBPF/C kernel programs and Go loaders up through FastAPI backends to React dashboards.

---

## 📌 Featured Projects

### [BeaconGuard — Behavioral Kernel Guard](https://github.com/dzdzdzdzdzdz213/beacon-guard)
> **eBPF-based runtime security monitor — hooks syscalls, builds per-process baselines, kills anomalies in real time**

```
eBPF (execve/open/connect/mmap/ptrace)  →  Ring buffer  →  Go loader
                                          →  Behavioral engine (profile + baseline + anomaly)
                                          →  Kill / Block / Alert  →  FastAPI  →  React dashboard
```

- **6 eBPF hook types**: execve, openat, tcp_v4_connect, udp_sendmsg, vm_mmap, ptrace
- **10 detection rules**: beaconing (variance analysis), reverse shell ports, DNS tunneling, mass deletion, sensitive file writes, unexpected binaries, executable mmap, ptrace injection
- **Learning mode**: 1-hour baseline auto-calibration, then enforcement
- **Low-variance beaconing detection** — finds periodic C2 callbacks by analyzing connection interval variance
- **Ring buffer + suspicion map** in kernel space, Go userspace with REST API + SSE streaming
- **React dashboard** with real-time timeline, process table, alert feed, live stats
- Docker Compose for full-stack deployment

---

### [ShieldWall — Network Security Monitor](https://github.com/dzdzdzdzdzdz213/cybersec-journey/tree/master/shieldwall)
> **Real-time IDS with plugin detection engine, MITRE ATT&CK mapping, and live dashboard**

```
FastAPI  →  Scapy packet capture  →  Plugin detectors (port scan, SQLi, DNS tunnel, brute force)
           →  MITRE ATT&CK enrichment  →  WebSocket  →  React + Recharts dashboard
```

- 8 built-in detection rules with hot-reloadable plugin system
- YAML config: auth, rate limiting, multi-interface capture, output sinks
- Output pipelines: **SQLite**, **Elasticsearch**, **Syslog**, **Webhook**, **Kafka**
- Docker Compose deployment with ES + Kibana + Redis
- 40+ MITRE ATT&CK technique mappings per alert

---

### [CloudSec Pipeline — GitOps Security Policy Engine](https://github.com/dzdzdzdzdzdz213/cloudsec-pipeline)
> **OPA/Rego policies blocking insecure infrastructure before it reaches production**

```
PR pushed (Terraform/K8s)  →  GitHub Actions  →  OPA policy evaluation
                                                →  Pass? ArgoCD deploys
                                                →  Fail? PR blocked
```

- **10 OPA policies**: 5 AWS (SGs, S3, IAM, encryption, logging) + 5 K8s (pods, resources, RBAC, network, namespaces)
- CI/CD integration: GitHub Actions checks every PR, posts results, blocks violations
- Gatekeeper constraint templates + ArgoCD app-of-apps for production K8s
- 17 OPA unit tests validating every policy rule
- Secure + insecure Terraform/K8s examples for testing
- Go CLI tool, Docker Compose local dev, Kind deployment script

---

### [Cybersec Journey — 50 Security Tools](https://github.com/dzdzdzdzdzdz213/cybersec-journey)
Monorepo of 50 independently-runnable tools spanning 7 security domains:

| Domain | Highlight Tools |
|--------|----------------|
| **Network Security** | Packet sniffer, IDS, DNS tunnel, port knocking, honeypot |
| **Cryptography** | Steganography, hash chains, ZK proofs, lattice crypto |
| **Digital Forensics** | Disk imager, file carver, memory analyzer, timeline builder |
| **Red Teaming** | C2 framework, payload dropper, lateral movement, keylogger |
| **Web Security** | SQLi/XSS scanner, JWT inspector, CSRF tester |
| **OSINT** | Domain fingerprinting, social mapper, WHOIS intelligence |
| **Malware Analysis** | YARA scanner, shellcode analyzer, behavioral graph |

---

## 🧰 Skills & Tools

```
Languages      C  ·  Go  ·  Python  ·  eBPF  ·  x86/x64 Assembly  ·  JavaScript  ·  PowerShell  ·  Rego
Frameworks     FastAPI  ·  React  ·  Recharts  ·  Scapy  ·  YARA  ·  libbpf
Infrastructure Docker  ·  Kubernetes  ·  ArgoCD  ·  OPA/Gatekeeper  ·  Terraform
Storage        SQLite  ·  PostgreSQL  ·  Elasticsearch  ·  Redis
Security       Network analysis  ·  Cryptography  ·  Forensics  ·  Malware analysis  ·  OSINT
```

---

## 📈 GitHub Stats

<div align="center">
  
  <a href="https://github.com/dzdzdzdzdzdz213">
    <img height="180em" src="https://github-readme-stats.vercel.app/api?username=dzdzdzdzdzdz213&show_icons=true&theme=dark&hide_border=true&include_all_commits=true&count_private=true" />
    <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=dzdzdzdzdzdz213&layout=compact&theme=dark&hide_border=true&langs_count=8" />
  </a>
  
  <br />
  
  [![BeaconGuard](https://github-readme-stats.vercel.app/api/pin/?username=dzdzdzdzdzdz213&repo=beacon-guard&theme=dark&hide_border=true&description_lines_count=2)](https://github.com/dzdzdzdzdzdz213/beacon-guard)
  [![CloudSec Pipeline](https://github-readme-stats.vercel.app/api/pin/?username=dzdzdzdzdzdz213&repo=cloudsec-pipeline&theme=dark&hide_border=true&description_lines_count=2)](https://github.com/dzdzdzdzdzdz213/cloudsec-pipeline)
  
</div>

---

<div align="center">
  
  *Building tools that make networks safer. Open to security engineering roles.*

  <a href="mailto:aimenmamache0@gmail.com"><img src="https://img.shields.io/badge/Email-aimenmamache0%40gmail.com-red?style=flat-square&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/dzdzdzdzdzdz213"><img src="https://img.shields.io/badge/GitHub-dzdzdzdzdzdz213-181717?style=flat-square&logo=github&logoColor=white" /></a>
  
</div>
