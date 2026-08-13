# Devsy Docker WSL Provider

This Devsy provider runs Docker workspaces in a selected WSL distribution by
calling the Windows `wsl.exe` launcher.

## Requirements

- Windows with WSL installed.
- A WSL distribution with Docker installed, running, and accessible to its
  default user.
- Devsy installed on Windows.

## Install

Add the provider manifest:

```powershell
devsy provider add .\provider.yaml
```

When prompted, set `WSL_DISTRIBUTION` to the distribution name shown by:

```powershell
wsl.exe --list --quiet
```

For example, use `Ubuntu` when `wsl.exe --list --quiet` includes `Ubuntu`.

The provider validates that Docker is available and its daemon is reachable in
the selected distribution before Devsy creates a workspace.
