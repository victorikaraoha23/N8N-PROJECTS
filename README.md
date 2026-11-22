# n8n Workflow Vault

A versioned collection of workflow exports and automation experiments from a self-hosted n8n environment.

- **Repository:** https://github.com/victorikaraoha23/N8N-PROJECTS
- **Purpose:** Preserve, review, and improve reusable automation workflows.
- **Status:** Active workflow archive; scheduled backup reliability is not claimed until independently verified.

## What is in the repository

Workflow exports are organized by snapshot date under `workflows/YYYY-MM-DD/`. The collection includes:

- A configurable AI gateway that accepts a prompt, validates provider settings, calls an OpenAI-compatible chat-completions endpoint, and returns a normalized result.
- An AI software-engineering department experiment that coordinates specialist roles such as CTO, backend, frontend, DevOps, QA, and security.
- Social-media publishing workflow experiments.
- A nightly workflow-export/backup workflow.
- OpenMontage-related research and workflow experiments, including intake, research, claim extraction, and evidence-verification stages.

The exported JSON files are the source of truth for the exact nodes and connections. Descriptions in this README are summaries, not a guarantee that every workflow is enabled or currently connected to working credentials.

## Repository layout

```text
workflows/
  YYYY-MM-DD/
    workflow-name.json
README.md
```

Dated snapshots preserve the evolution of workflow definitions. Repeated exports across dates may represent backup history rather than distinct products.

## Backup design

The intended backup schedule is daily at midnight in the `Africa/Lagos` timezone. The intended process is to export workflows from the self-hosted n8n instance and commit changed JSON exports to this repository.

**Important:** A workflow definition being present in this repository does not prove that the scheduled backup has run successfully or continuously. Check the n8n execution history and the latest Git commit before relying on a backup. This repository is not a complete n8n disaster-recovery backup: it does not, by itself, preserve the n8n database, credentials, binary data, or execution history.

## Security

- Never commit API keys, passwords, OAuth tokens, private keys, or credential values.
- n8n exports may contain credential names and credential identifiers; review exports before making them public.
- Store secrets in n8n credentials or the deployment environment, not in workflow node parameters.
- Treat workflow exports as executable automation definitions and review them before importing or activating them.

## Working with the exports

1. Inspect a workflow JSON file before importing it.
2. Confirm required n8n node types and versions are available on your instance.
3. Recreate credentials locally using your own secret values.
4. Test with non-production data.
5. Enable a workflow only after reviewing triggers, permissions, outbound requests, and failure handling.

## License and attribution

Check the source repository and individual workflow metadata before reusing third-party workflow designs or embedded assets. A workflow export in this repository is not automatically an original work or an unrestricted license grant.
