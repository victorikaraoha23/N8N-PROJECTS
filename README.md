n8n Workflow Vault

A GitHub repository for backing up and organizing workflows from my self-hosted n8n server.

Purpose

This repository will serve as the central storage location for my n8n workflows as I build more automations.

The goal is to automatically upload workflow exports to GitHub every midnight, preserving a history of changes and making workflows easier to manage and recover.

Backup Schedule

* Frequency: Every day
* Time: Midnight (12:00 AM)
* Timezone: Africa/Lagos
* Destination: This GitHub repository
* Method: Export n8n workflows and upload changes to GitHub

Repository Structure

n8n-workflow-vault/
├── README.md
├── workflows/
└── .gitignore

The workflows/ directory will contain exported n8n workflow files. Its organization can evolve as more workflows are created.

Backup Requirements

The backup automation should:

1. Run every midnight.
2. Export workflows from my n8n server.
3. Save the exported workflows in this repository.
4. Upload changes to GitHub.
5. Preserve Git history so previous versions can be reviewed.
6. Report backup failures rather than silently ignoring them.

Security

Sensitive credentials, API keys, passwords, and other secrets must not be committed to GitHub.

The repository should remain private unless I explicitly decide otherwise.

Scope

This repository is intended for n8n workflow definitions. It is not automatically a complete backup of the n8n server, its database, credentials, or execution history.

Project Status

The repository and midnight backup automation are intended to be set up. The backup process should be tested before being considered operational.
