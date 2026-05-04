<h1 align="center">Cybersecurity Labs (Docker / Podman)</h1>

<p align="center">
  Small, self-contained security labs you can run locally with the Docker CLI (Podman-compatible).<br/>
  Each lab includes a vulnerable build, a fixed build, and a short walkthrough.
</p>

<p align="center">
  <a href="https://github.com/DebaA17/cybersecurity-labs/actions/workflows/publish-images-ghcr.yml">
    <img alt="Build & Publish Images" src="https://github.com/DebaA17/cybersecurity-labs/actions/workflows/publish-images-ghcr.yml/badge.svg" />
  </a>
  <a href="./LICENSE">
    <img alt="License" src="https://img.shields.io/badge/License-MIT-green.svg" />
  </a>
  <img alt="Docker" src="https://img.shields.io/badge/Docker-Podman--compatible-2496ED?logo=docker&logoColor=white" />
</p>

## Labs

- 🐧 [Linux Privilege Escalation (sudo misconfiguration)](labs/linux-privilege-escalation/)
  - Start as a low-priv user in a container, enumerate, and escalate to `root`.
- 🌐 [Web Exploitation (SQL Injection)](labs/web-exploitation-sqli/)
  - Exploit a vulnerable Flask + SQLite login, then verify the fixed build.
- 📤 [Web Exploitation (File Upload)](labs/web-exploitation-file-upload/)
  - Compare weak upload handling vs a strict allowlist + safe storage.
- 🧾 [Web Exploitation (IDOR)](labs/web-exploitation-idor/)
  - Exploit missing authorization on `/profile/<id>`, then verify the fix.
- 🧩 [Web Exploitation (PHP Attack Chain)](labs/web-exploitation-php-attack-chain/)
  - See how unsafe upload handling and command execution become compromise.

All labs: [labs/](labs/)

## Prerequisites

- Docker CLI (Podman-compatible): `docker`
- Basic understanding of container usage (build, run, exec)
- Linux terminal familiarity recommended

## Safety / Scope

These labs are intentionally vulnerable.

- Run locally on a non-production machine.
- **Container root is not host root**, but it’s still a real security boundary lesson.

## Quick start

Each lab directory contains its own README with:

- image build commands (`docker build`)
- manual run commands (`docker run`, ports, network)
- exploit walkthrough (manual + optional script)
- secure fixed build/run steps

## License

MIT — see [LICENSE](LICENSE).

## Contact

[![GitHub](https://img.shields.io/badge/GitHub-DebaA17-181717?logo=github&logoColor=white)](https://github.com/DebaA17)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/debasis-biswas/)

