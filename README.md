# Cybersecurity Labs (Docker / Podman)

Small, self-contained security labs you can run locally with the Docker CLI (works with Podman too). Each lab ships a vulnerable build, a fixed build, and a short walkthrough.

## Labs

- **Linux Privilege Escalation Lab (sudo misconfiguration)**
  - Location: `labs/linux-privilege-escalation/`
  - You start as a low-privilege user inside a container and escalate to `root` due to an unsafe sudoers rule.

- **Web Exploitation Lab (SQL Injection)**
  - Location: `labs/web-exploitation-sqli/`
  - A tiny Flask app with a classic SQL injection login flaw, plus a fixed version using parameterized queries.

## Prerequisites
Docker CLI available (Docker is used as a Podman-compatible alias in this project): docker
Basic understanding of container usage (build, run, exec)
Linux terminal familiarity recommended

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

## Run from GHCR

This repo includes a GitHub Actions workflow that publishes images to GHCR. `docker run` will pull automatically if the image isn’t present locally.

```bash
# Linux privesc
docker run --rm -it ghcr.io/debaa17/cybersecurity-labs/privesc-sudo:vuln

# Web SQLi
docker run --rm -it -p 8080:8000 ghcr.io/debaa17/cybersecurity-labs/flask-sqli:vuln
```

