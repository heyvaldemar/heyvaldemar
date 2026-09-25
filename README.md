<div align="center">

# Vladimir Mikhalev

**Docker Captain · IBM Champion · CNCF Ambassador · AWS Community Builder**

</div>

---

### What I Do

One of fewer than 250 Docker Captains worldwide. 10 vendor-recognized community titles across Docker, IBM, CNCF, AWS, HashiCorp, Snyk, Cypress, Notion, GitKraken, and Platform Engineering, earned through contribution rather than credentials.

Every architecture recommendation backed by production experience. Designed and delivered cloud infrastructure at Amazon, IBM, Thales, and a Series D data platform serving Fortune 500 clients. I design scalable systems and publish what I learn: reference architectures for container security, AI governance, and platform engineering used by practitioners worldwide.

---

### Recognition

*Docker CEO on my contributions to the ecosystem*

<div align="center">

[![Docker CEO Scott Johnston recognizes Vladimir Mikhalev at Docker Captains Summit 2024](https://img.youtube.com/vi/NAv1e36PTB8/mqdefault.jpg)](https://www.youtube.com/watch?v=NAv1e36PTB8&t=58)

</div>

> *"Vladimir has written more than 100 pieces of content for Docker in the past year. He has also helped us find customer stories that we've been able to document and share throughout the rest of the community. And he's met with multiple product managers internally to share his product feedback."*
>
> — Scott Johnston, CEO, Docker (2019–2025)

**Snyk Ambassador Award Finalist** · [Four named first-hand references, with linked proof](https://heyvaldemar.com/provenance/)

---

### Published Work

*Selected publications on vendor platforms*

- **Docker Official Blog:** [The Untrusted Autonomous Workload: How AI Coding Agents Reshape What Isolation Has to Do](https://www.docker.com/blog/untrusted-autonomous-workload-ai-sandboxes/)
- **Docker Official Blog:** [How to Build, Run, and Package AI Models Locally with Docker Model Runner](https://www.docker.com/blog/how-to-build-run-and-package-ai-models-locally-with-docker-model-runner/)
- **Docker Official Blog:** [Testcontainers Cloud vs Docker-in-Docker for Testing Scenarios](https://www.docker.com/blog/testcontainers-cloud-vs-docker-in-docker-for-testing-scenarios/)
- **Docker Official Blog:** [Master Docker and VS Code: Supercharge Your Dev Workflow](https://www.docker.com/blog/master-docker-vs-code-supercharge-your-dev-workflow/)
- **Docker Official Blog:** [Mastering Docker and Jenkins: Build Robust CI/CD Pipelines](https://www.docker.com/blog/docker-and-jenkins-build-robust-ci-cd-pipelines/)
- **Docker Official Blog:** [How to Dockerize a React App](https://www.docker.com/blog/how-to-dockerize-a-react-app/)
- **Docker Official Blog:** [Dockerize WordPress: Simplify Your Site's Setup and Deployment](https://www.docker.com/blog/dockerize-wordpress-simplify-your-sites-setup-and-deployment/)
- **Docker Official Blog:** [8 Top Docker Tips & Tricks](https://www.docker.com/blog/8-top-docker-tips-tricks-for-2024/)
- **Docker Enterprise Case Study:** [Accelerating AI Infrastructure at Ataccama](https://www.docker.com/customer-stories/ataccama)
- **Docker Enterprise Case Study:** [25% Cost Savings via Container-First Strategy](https://www.docker.com/customer-stories/beauty-giant)
- **Docker YouTube:** [Why 'latest' Broke Our Staging](https://www.youtube.com/shorts/8I3eRoc6exA) · [Use Docker Scout to Catch Prod Bugs](https://www.youtube.com/shorts/DDDwoIhHRxs)
- **Featured by Cypress:** [Cypress Ambassador Spotlight: Vladimir Mikhalev](https://www.cypress.io/blog/cypress-ambassador-spotlight-vladimir-mikhalev)
- **Cypress Blog:** [Cypress in the Age of AI Agents](https://dev.to/cypress/cypress-in-the-age-of-ai-agents-orchestration-trust-and-the-tests-that-run-themselves-43go)
- **Cypress Blog:** [Docker + Cypress: Perfecting E2E Testing](https://dev.to/cypress/docker-cypress-in-2025-how-ive-perfected-my-e2e-testing-setup-4f7j)
- **Cypress Blog:** [Cypress Test Replay: The Ultimate Guide to Time-Travel Debugging](https://dev.to/cypress/cypress-test-replay-in-2025-the-ultimate-guide-to-time-travel-debugging-5485)
- **Book:** [Technical Editor of "Docker and Kubernetes Security"](https://www.dockersecurity.io/)
- **Open Source:** [70+ production-grade deployment blueprints](https://github.com/heyvaldemar) · [1,000,000+ Docker Hub pulls](https://hub.docker.com/r/heyvaldemar/aws-kubectl)

---

### Engineering Standard

*Formalized supply-chain hardening program for public deployment-template repositories*

**[Self-Host Repo Hardening Runbook](https://github.com/heyvaldemar/self-host-repo-hardening-runbook)** is a 7-phase program that brings deployment-template repositories to a supply-chain-hardened baseline: commit-SHA-pinned GitHub Actions with per-job permissions, digest-pinned upstream images with a daily freshness check, OpenSSF Scorecard, CI linting, Trivy upstream scanning.

**Reference implementations, two repository shapes with one hardening rigor:**

| Repository | Shape | Supply-chain surface |
| :--- | :--- | :--- |
| [aws-kubectl-docker](https://github.com/heyvaldemar/aws-kubectl-docker) | Image-publishing | Cosign keyless signing · SBOM (SPDX) · SLSA build provenance · Trivy SARIF · digest-pinned base · OpenSSF Scorecard |
| [keycloak-traefik-letsencrypt-docker-compose](https://github.com/heyvaldemar/keycloak-traefik-letsencrypt-docker-compose) | Deployment template | Digest-pinned upstream images · daily freshness check against the registry · daily CI deployment smoke · lint + Trivy scan · OpenSSF Scorecard · keyless-signed releases · SLSA build provenance |

<!-- fleet-summary:start -->
**[88 repositories under this standard](https://github.com/heyvaldemar/catalog)** — 49 self-hosted applications behind Traefik, 14 game servers, 6 other stacks, 8 Terraform pipelines on AWS, 11 operations tools and scripts. Every template is pinned by digest, boots in CI daily, upgrades from its previous release on the same volumes, and is released only after that passes. fleet-ops recounts them once a day and rewrites this line when a number changes; these last changed 2026-09-23 18:12 UTC.
<!-- fleet-summary:end -->

---

### Evidence, Not Green Checks

*How an AI agent is run on this fleet*

An AI agent does most of the typing across these repositories. It is fast, and it is wrong on a schedule. So nothing it writes ships on its word: a release is cut only after the release commit itself deploys, backs up and restores in CI, and every fleet rule is tested against a planted violation before it is trusted.

<!-- fleet-evidence:start -->
**Today: 73 restore scripts across 48 repositories, every one of them run by CI.** 835 releases are tagged across the fleet. 46 of 47 templates restored an older release's backup into the current release on a machine that had never run the stack, the fastest in 22 s. OpenSSF Scorecard, run by OpenSSF and not by me, puts the median at 7.2 across 96 repositories. fleet-ops recounts these once a day and rewrites this line when a number changes; these last changed 2026-09-25 00:38 UTC.
<!-- fleet-evidence:end -->

What those checks caught on 23 September 2026, the day that line was first written:

- **A team wiki whose backup logged `Data backup OK` for 12 days and 8 releases** while it archived a storage volume nothing writes to. The uploaded files were in no backup. [The fix](https://github.com/heyvaldemar/outline-keycloak-traefik-letsencrypt-docker-compose/commit/02dc203f0347ad1ee2ced5afa2c1324232f4d366) now restores a file through S3 in CI on every push.
- **On that day, all 72 restore scripts the fleet then carried, across 47 templates, had never been run by CI**, the oldest since May 2021. The tests had restored with their own copy of the commands. [One of the scripts, before and after](https://github.com/heyvaldemar/wordpress-traefik-letsencrypt-docker-compose/commit/cd271e5dc945f00c32aa9546d31799d37a664526): it refused to run on the stack it shipped with. All of them run the shipped script now, and a fleet rule fails any that stops.
- **Six mistakes by the agent itself in one day**, from [an apostrophe that stopped a backup loop](https://github.com/heyvaldemar/outline-keycloak-traefik-letsencrypt-docker-compose/commit/2605ffbe63f953ac8b93c29fe4ffa2ad371a541f) to [a database client the image does not ship](https://github.com/heyvaldemar/otrs-traefik-letsencrypt-docker-compose/commit/292f5b3ddae05b7af6746a0b3681f4de5dcf2814). None reached a release.

And on 24 September, the day after: **two defects in the fleet's own watcher, found and fixed before its morning run.** A test's fake failed the way the real function never does, so 116 green tests hid a crash; and three templates whose cron had changed the day before would have been reported sixty-two hours late. Both are in the ledger with the rule each produced. The same day every public repository gained a rule against rewriting `main` and, where it was missing, a security policy; OpenSSF Scorecard scores the result, and the evidence page repeats that score with every check below ten and what it means here.

On 24 September the clean-machine drill went from four templates to every template that ships a restore script, all 47, in one day: each one restores its previous release's backup into the current release on a runner that has never run the stack, weekly, and the time is on the evidence page beside the recovery point the template ships with. The line above counts them; a template whose drill fails is listed as failing and carries no time.

Green is a claim. A restore is evidence.

**[The evidence, with a restore measured on a clean machine](https://heyvaldemar.com/evidence/)** · **[Every finding, with the rule it produced](https://heyvaldemar.com/ledger/)** · **[The decisions, and what each one cost](https://heyvaldemar.com/decisions/)**

---

### Production Background

*Enterprise infrastructure architecture at Fortune 500 scale*

Sole architect and technology leader for North American operations at a Series D enterprise serving Fortune 500 clients. Designing scalable cloud architecture on AWS for enterprise accounts: container orchestration, zero trust governance, AI-augmented platforms, multi-region infrastructure.

Previously: Amazon, IBM, Thales. Designed disaster recovery architecture at scale, distributed systems across continents, reliability engineering for deployments processing millions of requests per minute.

Every architecture decision I publish is backed by production experience. **[Four named, first-hand references, each with linked proof](https://heyvaldemar.com/provenance/)**: from Docker's then-CEO, a published security author, and the lead of Snyk's ambassador program.

---

### Community Titles

*10 active vendor-recognized programs*

| Organization | Title | Domain |
| :--- | :--- | :--- |
| [**Docker**](https://www.docker.com/contributors/vladimir-mikhalev/) | Captain | Container architecture, security, and developer workflows |
| [**IBM**](https://www.ibm.com/community/ibm-champions/) | Champion | Enterprise AI, Cloud, Automation, HashiCorp/Terraform portfolio |
| [**AWS**](https://builder.aws.com/community/community-builders) | Community Builder | Cloud architecture, EKS, Serverless |
| [**CNCF**](https://www.cncf.io/people/ambassadors/) | Ambassador | Kubernetes and the cloud native ecosystem |
| [**HashiCorp**](https://www.hashicorp.com/en/ambassador/directory) | Ambassador | Terraform, Vault, infrastructure as code |
| [**Platform Engineering**](https://platformengineering.org/ambassador-program) | Ambassador | Internal Developer Platforms |
| [**Snyk**](https://snyk.io/snyk-ambassadors/directory/) | Ambassador | Application security, supply chain |
| [**Cypress**](https://www.cypress.io/ambassadors) | Ambassador | Test automation, AI agents in testing |
| [**GitKraken**](https://www.gitkraken.com/meet-the-gitkraken-ambassadors) | Ambassador | Git workflows, version control |
| [**Notion**](https://www.notion.so/notion/Notion-Ambassador-Program-45448f9b8e704c7bab254bd505c4717c) | Ambassador | Engineering knowledge management |

---

<div align="center">

**Vladimir Mikhalev**

Docker Captain · IBM Champion · CNCF Ambassador · AWS Community Builder

*The Verdict — production-tested analysis on YouTube. 100,000+ subscribers.*

[YouTube](https://www.youtube.com/@valdemar_ai?sub_confirmation=1) · [Blog](https://heyvaldemar.com) · [LinkedIn](https://www.linkedin.com/in/heyvaldemar/)

</div>
