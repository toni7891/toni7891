<h1 align="center">Hi, I'm Tony</h1>
<h3 align="center">Junior DevOps Engineer | Infrastructure • Cloud • Automation</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Linux-Ubuntu-E95420?logo=ubuntu&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-Containers-2496ED?logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-IaC-7B42BC?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-Cloud-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS_Bedrock-GenAI-FF9900?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-FastAPI-009688?logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb&logoColor=white" />
  <img src="https://img.shields.io/badge/Bash-Scripting-121011?logo=gnubash&logoColor=white" />
  <img src="https://img.shields.io/badge/Ollama-Local_LLM-000000?logo=ollama&logoColor=white" />
  <img src="https://img.shields.io/badge/Git-Version_Control-F05032?logo=git&logoColor=white" />
</p>

---

## About Me

I'm a Junior DevOps Engineer who builds things to learn things.

I built DeployGuard because I wanted to understand what safe Kubernetes deployments actually look like — canary rollouts, Prometheus gates, policy enforcement, auto-rollback. It's published on PyPI and Homebrew. I built an investment terminal to understand how AI-integrated backends work end-to-end. Both projects run CI/CD pipelines, ship real artifacts, and live on AWS.

Currently studying for AWS SAA and working toward running production-grade infrastructure on my own.

---

## 💼 Software Projects

### DeployGuard - Zero-to-Kubernetes Deployment CLI

CLI tool (`dg`, PyPI: `dg-deploy`) that takes a developer from zero to a safely-deployed FastAPI+Postgres service on Kubernetes in four commands:

```bash
dg init payments-api   # scaffold service, run guard
dg cost                # static cost report on infra
dg provision           # minikube (local) or k3s on EC2 Spot (aws)
dg deploy              # build, push, canary rollout, auto-rollback
```

- **Guard engine:** 7 policy rules (resource limits, probes, security context, image pinning, root user, privileged containers, IAM) + kubeconform schema validation + Trivy CVE scanning. Blocks deploy on any violation. Every finding includes why-it-matters and what-to-fix.
- **Deploy engine:** blue/green precheck with Rich Live panel, canary rollout at 10/50/100% via nginx-ingress weights, Prometheus error-rate gate at each step, auto-rollback on gate fail, Postgres audit log for every deploy event
- **Cost analysis:** Terraform static parse + infracost + 8 cost-policy rules before a single resource is provisioned
- **AWS target:** k3s on EC2 Spot via Terraform, ECR image registry, no NAT Gateway (~$6/mo running, ~$3.50/mo paused)
- **Local target:** minikube (profile: deployguard), ingress via `minikube addons enable ingress`
- **LLM module:** LM Studio adapter for LLM-assisted scaffold generation; AWS Bedrock adapter in progress
- **Published:** v0.1.0 on PyPI via GitHub Actions Trusted Publisher (OIDC, no stored secrets)
- **Test suite:** 26+ unit tests across guard, cost, deploy engine, rollout, precheck, metrics, audit, ECR, LLM, and a smoke E2E test gated on CI branch protection
- **Claude Code skill:** `/guard` for in-editor manifest review without running the full CLI

---

### 4RCH3R - Investment Terminal

Full-stack portfolio tracker with AI-powered investment insights.

- **Backend:** Python FastAPI, REST endpoints, real-time price data via yfinance
- **Database:** MongoDB Atlas, three-collection design per portfolio (positions, snapshots, trade log)
- **Frontend:** Vanilla JS modular architecture (state, charts, portfolio, modals, chat, detail views)
- **AI Chat:** Local LLM via LM Studio / Ollama with DuckDuckGo search augmentation
- **Cloud branch:** AWS Bedrock Guardrails, SSM Parameter Store, tax calculation with loss offset logic

> Local AI inference paired with cloud-grade guardrails for a production-ready deployment path.

---

## ☁️ Cloud

**Certification target:** AWS Solutions Architect - Associate

**Studying:** VPC design, EC2 & Auto Scaling, IAM, S3, high-availability architecture, cost optimization

**Hands-on:** AWS Bedrock Guardrails (LLM content filtering), AWS SSM Parameter Store (secure config management)

---

## 🛠 Tech Stack

| Area | Tools |
|---|---|
| **Infrastructure** | Linux (Ubuntu, Kali), networking, system troubleshooting |
| **DevOps** | Docker, Kubernetes, Terraform, Jenkins, Prometheus, GitHub Actions, Bash |
| **Cloud** | AWS (SAA in progress), Bedrock, SSM |
| **Backend** | Python, FastAPI, MongoDB Atlas, REST API design |
| **Frontend** | Vanilla JS |
| **AI / LLM** | AWS Bedrock Guardrails, LM Studio, Ollama, Claude Code, RAG with web search |

---

## 📊 GitHub Stats

<div align="center">
  <img src="https://streak-stats.demolab.com?user=toni7891&theme=dark&hide_border=true" />
  <br/><br/>
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=toni7891&theme=react-dark&hide_border=true" />
  <br/><br/>
  <img src="https://visitor-badge.laobi.icu/badge?page_id=toni7891.toni7891&left_color=grey&right_color=orange" />
  <br/><br/>
  <img src="https://raw.githubusercontent.com/toni7891/toni7891/output/github-snake-dark.svg" />
</div>

---

## 🏗 Homelab & Infrastructure

**Networking**
- Multi-router and multi-switch topologies with Cisco Catalyst 2960, SG200-18
- Static and dynamic routing (OSPF), VLAN segmentation, inter-VLAN routing
- Trunking (802.1Q), STP, gateway redundancy, VLSM-based subnet planning
- Local DNS filtering and traffic control at the network level

**Compute & Containers**
- Isolated Ubuntu container environments for reproducible development and testing (ARM)
- Raspberry Pi infrastructure services for network-level experimentation
- Container lifecycle management, environment reproducibility, failure scenario simulation

**Operations**
- Validated connectivity, failover behavior, and traffic flow through structured testing
- Troubleshooting exercises across networking, permissions, and service reliability

<p align="center">
  <img src="https://github.com/toni7891/devops-course/blob/2718947a3c0d4a6edc6aa61f726d1e8e136a07f5/my%20first%20website/HomeNet.drawio.png">
</p>

---

## 📈 Building Toward

- Kubernetes in production
- Infrastructure as Code at scale (Terraform)
- Full CI/CD pipelines
- Cloud-native, startup-grade systems

---

## 💡 Engineering Philosophy

> *"The unspoken in the building phase comes up in deployment."*

> *"If you can't deploy it, automate it, and scale it — you don't fully understand it."*

---

## ⚡ Recent Activity

<!--START_SECTION:activity-->
<!--END_SECTION:activity-->

---

## 📬 Contact

<p align="center">
  <a href="mailto:toni7891@gmail.com">
    <img src="https://img.shields.io/badge/Email-toni7891%40gmail.com-D14836?logo=gmail&logoColor=white" />
  </a>
</p>

---

<p align="center">
  Hi, I’m Tony. I’m a DevOps and Cloud Infrastructure Engineer who loves building resilient, automated systems from scratch handling everything from containerization to full CI/CD pipelines. I’m a self-driven learner with sharp troubleshooting instincts and a passion for owning the entire deployment process.
</p>


