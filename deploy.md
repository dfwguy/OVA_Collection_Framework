# Agent deployment entry point

Give this file and its source directory to Codex, Claude, or another deployment agent.

Read [repository rules](AGENTS.md), [overview](README.md), [agent handoff](AGENT_HANDOFF.md), [deployment](docs/deployment.md), [hooks](docs/hooks.md), [operations](docs/operations.md), [acceptance](docs/acceptance.md), and [hub handover](docs/handover.md).

## Discover and configure

Use the approved collector/controller and Slurm scope. Discover scheduler identity, accounting/completion sources, approved nodes and durable artifact roots. The collector consumes scheduler evidence; it does not probe GPUs or submit health tests. Obtain DGX/HGX hardware identity from the validation inventory and preserve its association with runs. Keep real inventory, secrets and raw evidence outside the source tree.

Check Python 3.12+, systemd, storage capacity, filesystem ownership and read access as the intended service identity. Copy [the configuration template](examples/cluster.example.json) to a private location. Set explicit site/cluster/epoch identity, narrow readable roots and durable source retention. Preserve existing Slurm hooks and plugins.

## Plan, install and start

Run `python3 tools/deploy.py plan --config /absolute/private/cluster.json --output /absolute/private/new-plan` and review the rendered units and paths. Each output directory must be fresh. Follow the deployment guide's `apply` procedure on the designated collector, including native completion configuration only when needed. Verify the installed service account, pinned dependencies, source access, first scans and enabled units from the installation receipt.

Open the loopback browser using the documented SSH tunnel. Use the generated credential file without copying credentials into chat or artifacts. Configure team access only through the documented authenticated proxy. Do not expose an unauthenticated listener.

## Capture and hand over

Commission capture before validation job 1. Integrate the supplied runner/manifest hooks with Rack Status, health checks and Exemplar. Exercise short, failed and cancelled jobs; reconcile against independent scheduler records; verify exact captured bytes and recovery. Follow the acceptance guide for restart/reboot and overhead checks. Arrays, federation and heterogeneous jobs need an adapter before inclusion.

Export with manifests and checksums according to the handover guide. Validate reconstruction in a separate directory. Import into the designated validation hub using its approved schema and retain provenance and gaps. Report measured capture coverage, unresolved sources, exact source identity, deployment receipt, browser URL, evidence paths and recovery checkpoint. Offline fixtures do not establish live capture completeness.
