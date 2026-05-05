# Nanobot Telecom Lab

Agent-based telecom diagnostics system built with Nanobot, running across local and remote machines.

## Overview

This project demonstrates how an AI agent can orchestrate system diagnostics, log analysis, security checks, and configuration monitoring across multiple machines.

## Architecture

- Local VM: `nanobot-vm`
- Remote VM: `telecom-node-1` (via Multipass)
- Communication: SSH (key-based auth)
- Agent: Nanobot
- Tools: Python scripts for diagnostics + analysis

## Local Skills

- `machine_diagnostics.py` — system health (CPU, disk, memory)
- `collect_logs.py` — gathers system logs
- `summarize_logs.py` — detects issues from logs
- `whats_wrong.py` — generates plain-English diagnosis
- `compare_text_docs.py` — diff between text files

## Remote Skills

- `remote_diagnostics.py` — runs health checks on remote VM
- `sync_files.py` — transfers files via SCP

## Complex Skills

- `security_audit.py` — identifies potentially sensitive processes
- `drift_detection.py` — detects config mismatches across machines

## Automation

- `cron_monitor.sh` — runs periodic checks and logs results

## Agent Layer

- `skills/telecom-lab-demo/skill.md` defines tool usage
- Nanobot executes workflows via natural language prompts

## Example Command

```bash
nanobot agent -m "Run full telecom lab check and summarize system health"
