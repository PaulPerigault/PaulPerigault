# Cloud & DevOps Engineer | [paulperigault.fr](https://paulperigault.fr)

I am Paul Perigault. I build small command-line tools and services in Go, describe infrastructure in OpenTofu, and run them through CI that pins every action and image. This page lists only what is public and what the code in those repositories shows.

## Context

This README replaces the version written in April 2026, which embedded third-party statistics images and listed technologies with no public repository behind them. In November 2026 I rebuilt my repositories one at a time with the same method: one command to run, tools pinned by digest or hash, secret scanning on the full history, a README whose sample output is generated. Repositories I no longer maintain (school projects, group work, unfinished code) are archived and private. Last reviewed on 2026-11-18.

## Published repositories

State read on GitHub on 2026-11-18.

| Repository | What it is | State |
| --- | --- | --- |
| [rsa-ct-analyzer](https://github.com/PaulPerigault/rsa-ct-analyzer) | Finds weak RSA keys in X.509 certificates and Certificate Transparency logs: small moduli, bad exponents, factorable keys, shared primes (batch GCD, pure Go). | Public since 2026-11-12. Last push 2026-11-18. |
| [GetUrlCloudRun](https://github.com/PaulPerigault/GetUrlCloudRun) | Read-only Go API that returns the URLs of Cloud Run services, with a deterministic fake provider for offline use and a tested OpenTofu deployment. | Public since 2026-11-12. Last push 2026-11-18. |
| [bigdata-ai-jobs-market](https://github.com/PaulPerigault/bigdata-ai-jobs-market) | HDFS, Hive, Spark and Jupyter in Docker Compose (images pinned by digest) on an AI job-market dataset, with a tested PySpark ETL. ESIEA coursework; the sample data is synthetic. | Public since 2026-11-13. Last push 2026-11-18. |
| [portfolio](https://github.com/PaulPerigault/portfolio) | Source of [paulperigault.fr](https://paulperigault.fr): Astro and Tailwind CSS, hosted on Cloudflare Pages, with Cloudflare, GitHub and OVH resources described in OpenTofu. | Public. Last push 2026-11-18. |
| [design-system](https://github.com/PaulPerigault/design-system) | Design tokens (DTCG), CSS, Astro components, guard rails, a CLI and an MCP server, published as nine `@paulperigault/*` npm packages. Documentation at [design.paulperigault.dev](https://design.paulperigault.dev). | Public. Last push 2026-11-14. |
| [cv-latex](https://github.com/PaulPerigault/cv-latex) | LaTeX CV compiled by GitHub Actions. | Public. |

## Technologies

Each technology below is linked to a file in a public repository that uses it.

- **Go**: [rsa-ct-analyzer](https://github.com/PaulPerigault/rsa-ct-analyzer/blob/main/go.mod), [GetUrlCloudRun](https://github.com/PaulPerigault/GetUrlCloudRun/blob/main/go.mod), static binaries with CGO off.
- **OpenTofu** and **Google Cloud Run**: [GetUrlCloudRun `infra/`](https://github.com/PaulPerigault/GetUrlCloudRun/tree/main/infra).
- **OpenTofu** with Cloudflare, GitHub and OVH providers, **Cloudflare Pages**: [portfolio `infra/`](https://github.com/PaulPerigault/portfolio/tree/develop/infra).
- **Docker** (multi-stage, non-root, images pinned by digest) and **Docker Compose**: [GetUrlCloudRun `Dockerfile`](https://github.com/PaulPerigault/GetUrlCloudRun/blob/main/Dockerfile), [bigdata-ai-jobs-market `compose.yaml`](https://github.com/PaulPerigault/bigdata-ai-jobs-market/blob/main/compose.yaml).
- **GitHub Actions**, pinned by commit SHA, with CodeQL, zizmor and OpenSSF Scorecard: [workflows of rsa-ct-analyzer](https://github.com/PaulPerigault/rsa-ct-analyzer/tree/main/.github/workflows).
- **Task**, **golangci-lint**, **govulncheck**, **gitleaks**, **Lefthook**, **Trivy**, pinned: [rsa-ct-analyzer `tools/go.mod`](https://github.com/PaulPerigault/rsa-ct-analyzer/blob/main/tools/go.mod) and [`Taskfile.yml`](https://github.com/PaulPerigault/rsa-ct-analyzer/blob/main/Taskfile.yml).
- **Python 3.11**, **PySpark**, **Hadoop HDFS**, **Hive**, **Jupyter**, **uv**: [bigdata-ai-jobs-market](https://github.com/PaulPerigault/bigdata-ai-jobs-market/blob/main/pyproject.toml).
- **TypeScript**, **Astro**, **Tailwind CSS**, **Vitest**, **Playwright**, axe: [portfolio `package.json`](https://github.com/PaulPerigault/portfolio/blob/develop/package.json), [design-system](https://github.com/PaulPerigault/design-system/blob/main/package.json).
- **Rust compiled to WebAssembly**: [design-system `crates/`](https://github.com/PaulPerigault/design-system/tree/main/crates).
- **LaTeX**: [cv-latex](https://github.com/PaulPerigault/cv-latex/tree/main/cv).

## Method

- `Taskfile.yml` is the single entry point; `task verify` runs format, lint, tests with the race detector, documentation checks and security scans.
- Dependencies and tools are pinned. GitHub Actions are pinned by commit SHA. Secrets are scanned in the working tree and in the whole history.
- Infrastructure is written, formatted and validated by tools; changes reach the cloud only through a reviewed plan, never from CI.
- Decisions that are not obvious go in an ADR in the repository.

## Limits

- Several repositories are private on purpose: group work, school archives and unfinished code. Their absence here is not an omission, and I do not list technologies that only appear in them.
- My apprenticeship work, mainly Java and Angular, is not visible on GitHub. It is on my CV and not claimed here.
- Where a repository was rebuilt from a clean base, its Git dates are the date of the rebuild, not the date of the original work; each README says so in its *Context* section.

## Contact

- Site: [paulperigault.fr](https://paulperigault.fr)
- LinkedIn: [paul-perigault](https://linkedin.com/in/paul-perigault)
- E-mail: contact@paulperigault.fr
