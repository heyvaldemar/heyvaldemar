<div align="center">

# Vladimir Mikhalev

**Docker Captain · CNCF Ambassador · IBM Champion**

</div>

---

### What I Do

AI agents now hold the keys: code, data, cloud accounts. I build the boundary around them, attack it myself and publish what held and what broke. In one cluster with no route to the internet, six models read planted instructions. With the tool's rules hidden from them, they tried to send data out 92 times. [The boundary refused all 92](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent). It is tested every week on AWS, Google Cloud and Azure.

Models will get smarter. The question stays: what may a machine do, and who proves it can do nothing else.


---

### Community Titles

11 vendor community titles, each awarded by the vendor's own program. [One of fewer than 250 Docker Captains worldwide](https://www.docker.com/community/captains/).

[Docker Captain](https://www.docker.com/contributors/vladimir-mikhalev/) · [CNCF Ambassador (2026–2028)](https://www.cncf.io/people/ambassadors/?p=vladimir-mikhalev) · [IBM Champion](https://www.credly.com/badges/c0b85821-c9f1-4446-a9af-6d43f67b893f) · [AWS Community Builder](https://builder.aws.com/community/@heyvaldemar) · [HashiCorp Ambassador (2024–2025)](https://www.hashicorp.com/en/ambassador/directory?q=mikhalev) · [Platform Engineering Ambassador](https://platformengineering.org/ambassador-program) · [Snyk Ambassador (2023–2026)](https://heyvaldemar.com/provenance/#gerald-crescione) · [Cypress Ambassador](https://www.cypress.io/ambassadors#ambassadors-profiles) · [GitKraken Ambassador](https://www.gitkraken.com/meet-the-gitkraken-ambassadors) · [Notion Ambassador](https://www.notion.so/notion/Notion-Ambassador-Program-45448f9b8e704c7bab254bd505c4717c) · [Coder Champion](https://coder.com/coder-champions)

---

### Selected Work

*Reference architectures, each tested in CI against the failure it exists to stop*

- **[kubernetes-air-gapped-ai-agent](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent)**: an AI agent in a Kubernetes cluster with no route to the internet, where open models meet planted instructions every day. With the tool's rules hidden from them, six models tried to send data out 92 times, and the boundary refused all 92. Scheduled runs on AWS, Google Cloud and Azure.
- **[agent-security-benchmark](https://github.com/heyvaldemar/agent-security-benchmark)**: one set of planted instructions, put to three agent boundaries through their signed releases. Nothing got out at any of them, while open models acted on up to 15 of 18 instructions at one boundary and on none at another.
- **[kubernetes-oscal-evidence](https://github.com/heyvaldemar/kubernetes-oscal-evidence)**: the flagship's admission policies turned into signed OSCAL assessment results an auditor can check: seven controls from NIST SP 800-53, the SSDF and the AI RMF, each resting on a test.
- **[aws-eks-reference-platform](https://github.com/heyvaldemar/aws-eks-reference-platform)**: a multi-tenant Amazon EKS platform delivered as Argo CD ApplicationSets, with 56 checks on a fresh kind cluster every day and a weekly run on a real AWS account. Found: an add-on build that leaves Argo CD unable to read the cluster, which no mocked plan showed.
- **[kubernetes-supply-chain-admission](https://github.com/heyvaldemar/kubernetes-supply-chain-admission)**: the cluster runs an image only if one build signed it and attached provenance, an SBOM and a scan from the last day. Found: the most common scanner gate passes an image the scanner could not read.

Open-source product: **[oxy-llm-gateway](https://github.com/heyvaldemar/oxy-llm-gateway)**, a self-hosted LLM gateway co-authored with [DevOpsPink](https://github.com/DevOpsPink): per-project budgets, data loss prevention, a kill switch and an audit row for every request.

**[Everything else, with what each one found](https://heyvaldemar.com/work/)** · reported upstream to [gVisor](https://github.com/gvisor/gvisor/issues/15756), [Kyverno](https://github.com/kyverno/kyverno/issues/18023) (fixed in [1.20.0](https://github.com/kyverno/kyverno/releases/tag/v1.20.0)), [Trivy](https://github.com/aquasecurity/trivy/discussions/11403), [kube-network-policies](https://github.com/kubernetes-sigs/kube-network-policies/issues/452), [Docker Sandboxes](https://github.com/docker/sbx-releases/issues/818) (fixed) and [Docker Hardened Images](https://github.com/docker-hardened-images/catalog/pull/685)

---

### Production Background

*Where the decisions come from*

I build the platforms, run the company-wide systems on top of them, and am the sole IT and DevOps engineer for North America. I run the infrastructure my frameworks are tested against: container orchestration, zero-trust governance, AI-augmented platform engineering and multi-region cloud architecture on AWS. I also build internal applications with AI coding agents to replace paid SaaS subscriptions.

Since 2019 I have helped enterprise customers deploy a data-management platform on Kubernetes in AWS, Azure, Google Cloud and on premises, including self-managed and air-gapped installs; today I am the Kubernetes and cloud expert for North America, advise customers' engineers on Terraform, CI/CD and GitOps, and answer customer security questionnaires. I built and run the Professional Services GitLab.

Earlier: operations and support roles at IBM, IPONWEB, Amazon and Thales (2016–2019).

What I recommend here, I have run myself, and the evidence is linked.

---

### Recognition

*Docker's then-CEO on video, and the people who worked with me on LinkedIn*

<div align="center">

[![Docker CEO Scott Johnston recognizes Vladimir Mikhalev at Docker Captains Summit 2024](https://img.youtube.com/vi/NAv1e36PTB8/mqdefault.jpg)](https://www.youtube.com/watch?v=NAv1e36PTB8&t=58)

</div>

> *"Vladimir has written more than 100 pieces of content for Docker in the past year. He has also helped us find customer stories that we've been able to document and share throughout the rest of the community. And he's met with multiple product managers internally to share his product feedback."*
>
> **Scott Johnston**, CEO, Docker (2019–2025)

> *"Vladimir consistently ranked among the top three for sustained contribution in a program that had over 50 ambassadors across all continents at its peak at the time … He is one of the strongest security practitioners I have worked with anywhere."*
>
> **Gérald Crescione**, Head of AI Security Engineers Community, Snyk ([recommendation on LinkedIn](https://www.linkedin.com/in/heyvaldemar/details/recommendations/))

> *"Vladimir has exceptional ability to get from vague problem description to a design that fits the real world situation. He plainly explains trade-offs so they are understandable to both engineering and non-engineering audience."*
>
> **Marek Ovcacek**, former Field CTO at a data-management software company ([recommendation on LinkedIn](https://www.linkedin.com/in/heyvaldemar/details/recommendations/))

**Snyk Ambassador Award finalist (2023)** · [Every recommendation and named reference, with linked proof](https://heyvaldemar.com/provenance/)

---

### Published Work

*Selected publications on vendor platforms*

- **Docker Enterprise Case Study:** [25% Cost Savings via Container-First Strategy](https://www.docker.com/customer-stories/beauty-giant)
- **Docker Official Blog:** eight articles, the latest [The Untrusted Autonomous Workload: How AI Coding Agents Reshape What Isolation Has to Do](https://www.docker.com/blog/untrusted-autonomous-workload-ai-sandboxes/) ([all of them](https://www.docker.com/contributors/vladimir-mikhalev/))
- **Platform Engineering:** [One pull request, two walls: Onboarding teams onto a shared EKS platform](https://platformengineering.org/blog/one-pull-request-two-walls-onboarding-teams-shared-eks-platform) (November 2026), onboarding a team onto a shared EKS platform behind an allow-list Argo CD project and sync impersonation, tested on kind in CI
- **Book:** Technical Editor of [Docker and Kubernetes Security](https://dev.to/docker/i-just-published-my-book-docker-and-kubernetes-security-17lo) (2025), a [DevOps Dozen 2025 finalist](https://devops.com/devops-dozen-2025-finalists-announced/) for Best DevOps Book of the Year; Amazon credits me as [Editor](https://www.amazon.com/dp/B0FJY9DJR4)
- **Cypress:** [Ambassador Spotlight](https://www.cypress.io/blog/cypress-ambassador-spotlight-vladimir-mikhalev) · three articles for [Cypress on DEV](https://dev.to/cypress)
- **Open source:** [70+ deployment blueprints](https://github.com/heyvaldemar) · [1.8M+ Docker Hub pulls (aws-kubectl)](https://hub.docker.com/r/heyvaldemar/aws-kubectl), the default image of the ECR registry helper in [OpenMetadata's Helm chart](https://github.com/open-metadata/hybrid-ingestion-runner-helm-chart/blob/main/charts/hybrid-ingestion-runner/values.yaml)

---

### How I Work

*Evidence, not green checks*

An AI agent does most of the typing across these repositories, and nothing it writes ships on its word. It is fast, and it is wrong on a schedule, so a release is cut only after the release commit itself deploys, backs up and restores in CI, and every fleet rule is tested against a planted violation before it is trusted.

<!-- fleet-evidence:start -->
**Today: 76 restore scripts across 50 repositories, every one of them run by CI.** 2642 releases are tagged across the fleet. 45 of 47 templates restored an older release's backup into the current release on a machine that had never run the stack, the fastest in 18 s. OpenSSF Scorecard, run by OpenSSF and not by me, puts the median at 7.5 across 122 repositories. The OpenSSF Best Practices badge, a questionnaire I answered and OpenSSF publishes with every answer, is passing on 104 of 104 registered repositories. The 18 public repositories that hold no code to rate, this profile among them, are not registered. fleet-ops recounts these once a day and rewrites this line when a number changes; these last changed 2026-11-27 16:56 UTC.
<!-- fleet-evidence:end -->

Every template follows one hardening standard, the **[Self-Host Repo Hardening Runbook](https://github.com/heyvaldemar/self-host-repo-hardening-runbook)**: actions pinned by commit, images pinned by digest with a daily freshness check, OpenSSF Scorecard, and a Trivy scan of every upstream image. Three repository shapes, one rigor:

| Repository | Shape | Supply-chain surface |
| :--- | :--- | :--- |
| [aws-kubectl-docker](https://github.com/heyvaldemar/aws-kubectl-docker) | Image-publishing | Cosign keyless signing · SBOM (SPDX) · SLSA build provenance · Trivy SARIF · digest-pinned base · OpenSSF Scorecard |
| [keycloak-traefik-letsencrypt-docker-compose](https://github.com/heyvaldemar/keycloak-traefik-letsencrypt-docker-compose) | Deployment template | Digest-pinned upstream images · daily freshness check against the registry · daily CI deployment smoke · lint + Trivy scan · OpenSSF Scorecard · OpenSSF Best Practices passing · keyless-signed releases · SLSA build provenance |
| [fleet-ops](https://github.com/heyvaldemar/fleet-ops) | The automation that runs the fleet | Lint · OpenSSF Scorecard · OpenSSF Best Practices passing · keyless-signed releases · SLSA build provenance |

<!-- fleet-summary:start -->
**[109 repositories under this standard](https://github.com/heyvaldemar/catalog)**: 51 self-hosted applications behind Traefik, 17 game servers, 10 other stacks, 8 Terraform pipelines on AWS, 11 Kubernetes platforms, 1 LLM gateway, 11 operations tools and scripts. Every template is pinned by digest, boots in CI daily, upgrades from its previous release on the same volumes, and is released only after that passes. fleet-ops recounts them once a day and rewrites this line when a number changes; these last changed 2026-11-16 03:18 UTC.
<!-- fleet-summary:end -->

Green is a claim. A restore is evidence.

**[The evidence, with a restore measured on a clean machine](https://heyvaldemar.com/evidence/)** · **[Every finding, with the rule it produced](https://heyvaldemar.com/ledger/)** · **[The decisions, and what each one cost](https://heyvaldemar.com/decisions/)**

---

<div align="center">

**Vladimir Mikhalev**

Docker Captain · CNCF Ambassador · IBM Champion

*The Verdict: production-tested analysis on YouTube.*

[YouTube](https://www.youtube.com/@valdemar_ai?sub_confirmation=1) · [Blog](https://heyvaldemar.com) · [LinkedIn](https://www.linkedin.com/in/heyvaldemar/)

</div>
