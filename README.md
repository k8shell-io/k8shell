# k8shell — Issues & Feedback

This repository is the single inbox for bug reports, feature requests, and support questions for the k8shell platform.

Before opening an issue, search [existing issues](../../issues) to avoid duplicates and check the [documentation](https://github.com/k8shell-io/k8shell#readme) — your answer may already be there.

## Issue guidelines

- Use the issue template that best matches your report.
- Describe what you were doing, not which service you think is at fault — the team will identify that from the logs.
  - ❌ _"It doesn't work"_
  - ✅ _"Workspace pod never starts after provisioning — stuck in Pending"_
- One topic per issue — don't combine multiple bugs or requests.
- Use GitHub reactions (👍) rather than "+1" comments.

## Bug reports

Since k8shell is composed of multiple services, the most useful information you can provide is:

- **What you were doing** (e.g. provisioning a workspace, opening an SSH connection)
- **What failed** — the error message or unexpected behaviour you observed
- **Logs** from the k8shell services and workspaces namespaces:
  ```bash
  kubectl logs <pod-name> -n <k8shell-namespace>
  ```
  If the issue happens inside a workspace pod, you can get logs from inside the workspace:
  ```bash
  kbox logs
  ```
  or use the equivalent `kubectl` command:
  ```bash
  kubectl logs <workspace-pod> -n <workspaces-namespace>
  ```
- **k8shell Helm chart version** and any values overrides
- **Kubernetes distribution and version**

Attach large files by dragging and dropping a `.txt` file onto the issue comment box.

The team will use the logs to identify which service is involved and route the issue accordingly.
