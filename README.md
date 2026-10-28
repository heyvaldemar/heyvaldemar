<div align="center">

# Vladimir Mikhalev

**Docker Captain · CNCF Ambassador · IBM Champion**

</div>

---

### What I Do

I test what ships and publish what I find, failures included: 100+ public repositories, every restore script run by CI, every finding on [the ledger](https://heyvaldemar.com/ledger/) with its rule. [One of fewer than 250 Docker Captains worldwide](https://www.docker.com/community/captains/). 10 vendor community titles across Docker, IBM, CNCF, AWS, HashiCorp, Snyk, Cypress, Notion, GitKraken, and Platform Engineering, earned through contribution rather than credentials.

I design cloud and container platforms on Kubernetes, Terraform and AWS, secure their software supply chain, and explain the trade-offs to engineers, customers and leadership. The repositories below are reference architectures, and each says so. Earlier: operations and support roles at IBM, IPONWEB, Amazon and Thales (2016–2019).

---

### Recognition

*Docker's then-CEO on video, and three program leads on LinkedIn*

<div align="center">

[![Docker CEO Scott Johnston recognizes Vladimir Mikhalev at Docker Captains Summit 2024](https://img.youtube.com/vi/NAv1e36PTB8/mqdefault.jpg)](https://www.youtube.com/watch?v=NAv1e36PTB8&t=58)

</div>

> *"Vladimir has written more than 100 pieces of content for Docker in the past year. He has also helped us find customer stories that we've been able to document and share throughout the rest of the community. And he's met with multiple product managers internally to share his product feedback."*
>
> **Scott Johnston**, CEO, Docker (2019–2025)

> *"Vladimir belongs to a small group of Captains whose work has shaped Docker's developer ecosystem while setting the standard for technical communication in our community."*
>
> **Eva Bojorges**, Senior Developer Relations Manager, Docker, Inc. ([recommendation on LinkedIn](https://www.linkedin.com/in/heyvaldemar/details/recommendations/))

> *"Vladimir consistently ranked among the top three for sustained contribution in a program that had over 50 ambassadors across all continents at its peak at the time … He is one of the strongest security practitioners I have worked with anywhere."*
>
> **Gérald Crescione**, Head of AI Security Engineers Community, Snyk ([recommendation on LinkedIn](https://www.linkedin.com/in/heyvaldemar/details/recommendations/))

> *"He brought us well-developed drafts he had written himself, with customer results already gathered and a clear understanding of both the technical work and its business impact."*
>
> **Dan Stelzer**, partner marketing and the customer case study program, Docker ([recommendation on LinkedIn](https://www.linkedin.com/in/heyvaldemar/details/recommendations/))

**Snyk Ambassador Award finalist (2023)** · [Named first-hand references, with linked proof](https://heyvaldemar.com/provenance/)

---

### Reference Architectures

*Kubernetes, tested every day on kind, and weekly on a real AWS account from 21 October 2026; every claim is a check that fails the build*

- **[kubernetes-air-gapped-ai-agent](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent)**: an AI agent in a Kubernetes cluster with no route to the internet. Everything it runs crosses in as one signed file; the model is a reproducible image signed with the operator's key and carrying a signed AI-BOM, and admission checks both offline before the model server may mount it. Its tools go through the sandbox's MCP server, which holds the email tool's recipient to the company's domain, and its models sit behind one gateway that routes each request to the model it names and limits each client. Every day six open-weights models from four makers go through the same fifteen tasks with instructions planted in what they read: in [the run v1.1.0 was cut from](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent/actions/runs/39157806610) they acted on between none and half of them, and nothing left the company for any of the six, at $0.0001 to $0.0003 of model-server time a task; the [table](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent/blob/status/leaderboard.md) is rewritten after every run. Part of the models' restraint turned out to be the model server's: [with the tool schema's pattern hidden from them](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent/blob/main/docs/decisions/0013-the-decoder-is-a-control.md), all six tried to send data outside, 92 times, and the tool server refused every attempt. A review of its own checks found a way out by DNS through the kind node that every release before [v1.5.0](https://github.com/heyvaldemar/kubernetes-air-gapped-ai-agent/releases/tag/v1.5.0) had; it is closed, and tried on every run.
- **[aws-eks-reference-platform](https://github.com/heyvaldemar/aws-eks-reference-platform)**: a multi-tenant platform for Amazon EKS, delivered as Argo CD ApplicationSets. Admission policies compiled into native ValidatingAdmissionPolicies keep refusing with Kyverno stopped, tenants are confined by their own Argo CD projects and enforced sync impersonation, and a daily drill restores a deleted tenant from backup. Thirteen decision records, each ending with how the choice would be explained to a customer, a threat model and a Well-Architected review. 56 checks on a fresh cluster every day, and 56 again after upgrading one from the previous release. The AWS side runs every week on a real account: the first passing run, on 15 October 2026, applied 101 resources, brought every Application up on EKS 1.37, passed 14 checks against AWS, tore everything down and cost about $0.20. The seven runs before it found what no mocked plan could, among them an EKS add-on build that leaves Argo CD unable to read the cluster.
- **[kubernetes-ai-agent-sandbox](https://github.com/heyvaldemar/kubernetes-ai-agent-sandbox)**: what an AI agent that has been talked into something can reach. gVisor as the kernel boundary, an egress allowlist with a second wall at the destination, and one door to the tools: an MCP server that knows which agent is calling, grants each one named tools, holds the credentials no agent pod may carry, and logs every call. A demo agent is fooled on purpose in every run, and the official MCP SDK drives the server in CI. It found that on a node with swap, a gVisor pod's memory limit is not the limit. [v1.2.0](https://github.com/heyvaldemar/kubernetes-ai-agent-sandbox/releases/tag/v1.2.0) closed a way out its threat model had accepted, lookups through the cluster's DNS, and found that kind's network plugin lets a new pod's first packets through before its network policy applies.
- **[kubernetes-supply-chain-admission](https://github.com/heyvaldemar/kubernetes-supply-chain-admission)**: the cluster runs an image only if one build signed it and attached provenance, an SBOM and a scan from the last day. It found that the most common scanner gate passes an image the scanner could not read, and that Kyverno's image policy can read the wrong attestation when a registry lists them out of order.
- **[kubernetes-postgres-recovery](https://github.com/heyvaldemar/kubernetes-postgres-recovery)**: PostgreSQL on CloudNativePG, restored every day three ways: to a second before a `DROP TABLE`, onto a standby after the primary is killed mid-write with no acknowledged write lost, and from the bucket alone after the cluster and its volumes are deleted. It found that a cluster can report Ready while it backs up nothing.

Reported upstream from these repositories: [gVisor](https://github.com/google/gvisor/issues/15756), [Kyverno](https://github.com/kyverno/kyverno/issues/18023) with a reproduction, [Kyverno and image volumes](https://github.com/kyverno/kyverno/pull/17555#issuecomment-6245868388) with a tested workaround, [a split of a Kyverno fix](https://github.com/kyverno/kyverno/issues/18000#issuecomment-6159962152) that has since merged, [Kyverno's docs](https://github.com/kyverno/website/pull/2201), [Trivy](https://github.com/aquasecurity/trivy/discussions/11403) and [metrics-server on EKS](https://github.com/kubernetes-sigs/metrics-server/issues/1868#issuecomment-6195863017).

---

### Published Work

*Selected publications on vendor platforms*

- **Docker Official Blog:** [The Untrusted Autonomous Workload: How AI Coding Agents Reshape What Isolation Has to Do](https://www.docker.com/blog/untrusted-autonomous-workload-ai-sandboxes/)
- **Docker Official Blog:** [How to Build, Run, and Package AI Models Locally with Docker Model Runner](https://www.docker.com/blog/how-to-build-run-and-package-ai-models-locally-with-docker-model-runner/)
- **Docker Official Blog:** [Testcontainers Cloud vs Docker-in-Docker for Testing Scenarios](https://www.docker.com/blog/testcontainers-cloud-vs-docker-in-docker-for-testing-scenarios/)
- **Docker Official Blog:** [Master Docker and VS Code: Supercharge Your Dev Workflow](https://www.docker.com/blog/master-docker-vs-code-supercharge-your-dev-workflow/)
- **Docker Official Blog:** [Mastering Docker and Jenkins: Build Robust CI/CD Pipelines](https://www.docker.com/blog/docker-and-jenkins-build-robust-ci-cd-pipelines/)
- **Docker Official Blog:** [How to Dockerize a React App](https://www.docker.com/blog/how-to-dockerize-react-app/) (with Kristiyan Velkov)
- **Docker Official Blog:** [Dockerize WordPress: Simplify Your Site's Setup and Deployment](https://www.docker.com/blog/how-to-dockerize-wordpress/)
- **Docker Official Blog:** [8 Top Docker Tips & Tricks](https://www.docker.com/blog/8-top-docker-tips-tricks-for-2024/)
- **Docker Enterprise Case Study:** [Accelerating AI Infrastructure at Ataccama](https://www.docker.com/customer-stories/ataccama)
- **Docker Enterprise Case Study:** [25% Cost Savings via Container-First Strategy](https://www.docker.com/customer-stories/beauty-giant)
- **Docker YouTube:** [Why 'latest' Broke Our Staging](https://www.youtube.com/shorts/8I3eRoc6exA) · [Make your security team happy (#captainslog 02)](https://www.youtube.com/shorts/DDDwoIhHRxs)
- **Featured by Cypress:** [Cypress Ambassador Spotlight: Vladimir Mikhalev](https://www.cypress.io/blog/cypress-ambassador-spotlight-vladimir-mikhalev)
- **3 articles for [Cypress on DEV](https://dev.to/cypress):** [Cypress in the Age of AI Agents](https://dev.to/cypress/cypress-in-the-age-of-ai-agents-orchestration-trust-and-the-tests-that-run-themselves-43go) · [Docker + Cypress: Perfecting E2E Testing](https://dev.to/cypress/docker-cypress-in-2025-how-ive-perfected-my-e2e-testing-setup-4f7j) · [Cypress Test Replay: The Ultimate Guide to Time-Travel Debugging](https://dev.to/cypress/cypress-test-replay-in-2025-the-ultimate-guide-to-time-travel-debugging-5485)
- **Book:** Technical Editor of [Docker and Kubernetes Security](https://dev.to/docker/i-just-published-my-book-docker-and-kubernetes-security-17lo) (2025), a [DevOps Dozen 2025 finalist](https://devops.com/devops-dozen-2025-finalists-announced/) for Best DevOps Book of the Year. Retail record: [Goodreads](https://www.goodreads.com/book/show/242196088)
- **Open Source:** [70+ open-source deployment blueprints](https://github.com/heyvaldemar), [maintained with AI coding agents under policy gates I prove with planted violations](https://github.com/heyvaldemar/fleet-ops) · [1.5M+ Docker Hub pulls (aws-kubectl)](https://hub.docker.com/r/heyvaldemar/aws-kubectl)
- **Third-party adoption:** aws-kubectl is the default image of the ECR registry helper in [OpenMetadata's Helm chart](https://github.com/open-metadata/hybrid-ingestion-runner-helm-chart/blob/main/charts/hybrid-ingestion-runner/values.yaml)

---

### Engineering Standard

*Formalized supply-chain hardening program for public deployment-template repositories*

**[Self-Host Repo Hardening Runbook](https://github.com/heyvaldemar/self-host-repo-hardening-runbook)** is an 8-phase program that brings deployment-template repositories to a supply-chain-hardened baseline: commit-SHA-pinned GitHub Actions with per-job permissions, digest-pinned upstream images with a daily freshness check, OpenSSF Scorecard, CI linting, Trivy upstream scanning.

**Reference implementations, three repository shapes with one hardening rigor:**

| Repository | Shape | Supply-chain surface |
| :--- | :--- | :--- |
| [aws-kubectl-docker](https://github.com/heyvaldemar/aws-kubectl-docker) | Image-publishing | Cosign keyless signing · SBOM (SPDX) · SLSA build provenance · Trivy SARIF · digest-pinned base · OpenSSF Scorecard |
| [keycloak-traefik-letsencrypt-docker-compose](https://github.com/heyvaldemar/keycloak-traefik-letsencrypt-docker-compose) | Deployment template | Digest-pinned upstream images · daily freshness check against the registry · daily CI deployment smoke · lint + Trivy scan · OpenSSF Scorecard · OpenSSF Best Practices passing · keyless-signed releases · SLSA build provenance |
| [fleet-ops](https://github.com/heyvaldemar/fleet-ops) | The automation that runs the fleet | Lint · OpenSSF Scorecard · OpenSSF Best Practices passing · keyless-signed releases · SLSA build provenance |

<!-- fleet-summary:start -->
**[100 repositories under this standard](https://github.com/heyvaldemar/catalog)**: 51 self-hosted applications behind Traefik, 17 game servers, 7 other stacks, 8 Terraform pipelines on AWS, 6 Kubernetes platforms, 11 operations tools and scripts. Every template is pinned by digest, boots in CI daily, upgrades from its previous release on the same volumes, and is released only after that passes. fleet-ops recounts them once a day and rewrites this line when a number changes; these last changed 2026-10-27 22:25 UTC.
<!-- fleet-summary:end -->

---

### Evidence, Not Green Checks

*How an AI agent is run on this fleet*

An AI agent does most of the typing across these repositories, and nothing it writes ships on its word. It is fast, and it is wrong on a schedule, so a release is cut only after the release commit itself deploys, backs up and restores in CI, and every fleet rule is tested against a planted violation before it is trusted.

<!-- fleet-evidence:start -->
**Today: 76 restore scripts across 50 repositories, every one of them run by CI.** 1721 releases are tagged across the fleet. 47 of 47 templates restored an older release's backup into the current release on a machine that had never run the stack, the fastest in 20 s. OpenSSF Scorecard, run by OpenSSF and not by me, puts the median at 7.3 across 109 repositories. The OpenSSF Best Practices badge, a questionnaire I answered and OpenSSF publishes with every answer, is passing on 102 of 102 registered repositories. The 7 public repositories that hold no code to rate, this profile among them, are not registered. fleet-ops recounts these once a day and rewrites this line when a number changes; these last changed 2026-10-28 14:14 UTC.
<!-- fleet-evidence:end -->

What those checks caught on 23 September 2026, the day that line was first written:

- **A team wiki whose backup logged `Data backup OK` for 12 days and 8 releases** while it archived a storage volume nothing writes to. The uploaded files were in no backup. [The fix](https://github.com/heyvaldemar/outline-keycloak-traefik-letsencrypt-docker-compose/commit/02dc203f0347ad1ee2ced5afa2c1324232f4d366) now restores a file through S3 in CI on every push.
- **On that day, all 72 restore scripts the fleet then carried, across 47 templates, had never been run by CI**, the oldest since May 2021. The tests had restored with their own copy of the commands. [One of the scripts, before and after](https://github.com/heyvaldemar/wordpress-traefik-letsencrypt-docker-compose/commit/cd271e5dc945f00c32aa9546d31799d37a664526): it refused to run on the stack it shipped with. All of them run the shipped script now, and a fleet rule fails any that stops.
- **Five mistakes by the agent itself in one day**, from [an apostrophe that stopped a backup loop](https://github.com/heyvaldemar/outline-keycloak-traefik-letsencrypt-docker-compose/commit/2605ffbe63f953ac8b93c29fe4ffa2ad371a541f) to [a database client the image does not ship](https://github.com/heyvaldemar/otrs-traefik-letsencrypt-docker-compose/commit/292f5b3ddae05b7af6746a0b3681f4de5dcf2814). None reached a release.

And on 24 September, the day after: **two defects in the fleet's own watcher, found and fixed before its morning run.** A test's fake failed the way the real function never does, so 116 green tests hid a crash; and three templates whose cron had changed the day before would have been reported sixty-two hours late. Both are in the ledger with the rule each produced. The same day every public repository gained a rule against rewriting `main` and, where it was missing, a security policy; OpenSSF Scorecard scores the result, and the evidence page repeats that score with every check below ten and what it means here.

On 24 September the clean-machine drill went from four templates to every template that ships a restore script, all 47, in one day: each one restores its previous release's backup into the current release on a runner that has never run the stack, weekly, and the time is on the evidence page beside the recovery point the template ships with. The line above counts them; a template whose drill fails is listed as failing and carries no time.

Green is a claim. A restore is evidence.

**[The evidence, with a restore measured on a clean machine](https://heyvaldemar.com/evidence/)** · **[Every finding, with the rule it produced](https://heyvaldemar.com/ledger/)** · **[The decisions, and what each one cost](https://heyvaldemar.com/decisions/)**

---

### Production Background

*Where the decisions come from*

I build the platforms, run the company-wide systems on top of them, and am the sole IT and DevOps engineer for North America. I am the Kubernetes and cloud expert on customer calls, answer customer security questionnaires, and run a production platform on Amazon EKS with Terraform and GitHub Actions. I drove the container platform decision (Docker over Podman) for moving legacy applications to containers, and I am the customer-side voice of [Docker's enterprise customer story](https://www.docker.com/customer-stories/ataccama) on that move: 75% faster deployments and 40% fewer servers.

Earlier: operations and support roles at IBM, IPONWEB, Amazon and Thales (2016–2019).

The decisions I publish come from production work. **[Named first-hand references, each with linked proof](https://heyvaldemar.com/provenance/)**: from Docker's then-CEO, the Docker Captains program lead, the lead of Docker's customer case study program, a published security author, and the lead of Snyk's ambassador program.

---

### Community Titles

*10 vendor community titles*

| Organization | Title | Domain |
| :--- | :--- | :--- |
| [**Docker**](https://www.docker.com/contributors/vladimir-mikhalev/) | Captain | Container architecture, security, and developer workflows |
| [**IBM**](https://www.ibm.com/community/ibm-champions/) | Champion | Enterprise AI, Cloud, Automation, HashiCorp/Terraform portfolio |
| [**AWS**](https://builder.aws.com/community/community-builders) | Community Builder | Cloud architecture, EKS, Serverless |
| [**CNCF**](https://www.cncf.io/blog/2026/10/06/2026-2028-cncf-ambassador-cohort/) | Ambassador (2026-2028 cohort) | Kubernetes and the cloud native ecosystem |
| [**HashiCorp**](https://www.hashicorp.com/en/ambassador/directory?q=mikhalev) | Ambassador (2024-2025), continuing as IBM Champion 2026 | Terraform, Vault, infrastructure as code |
| [**Platform Engineering**](https://platformengineering.org/ambassador-program) | Ambassador | Internal Developer Platforms |
| [**Snyk**](https://snyk.io/snyk-ambassadors/directory/) | Ambassador (2023-2026), Ambassador Award finalist (2023) | Application security, supply chain |
| [**Cypress**](https://www.cypress.io/ambassadors) | Ambassador | Test automation, AI agents in testing |
| [**GitKraken**](https://www.gitkraken.com/meet-the-gitkraken-ambassadors) | Ambassador | Git workflows, version control |
| [**Notion**](https://www.notion.so/notion/Notion-Ambassador-Program-45448f9b8e704c7bab254bd505c4717c) | Ambassador | Engineering knowledge management |

---

<div align="center">

**Vladimir Mikhalev**

Docker Captain · CNCF Ambassador · IBM Champion

*The Verdict: production-tested analysis on YouTube.*

[YouTube](https://www.youtube.com/@valdemar_ai?sub_confirmation=1) · [Blog](https://heyvaldemar.com) · [LinkedIn](https://www.linkedin.com/in/heyvaldemar/)

</div>
