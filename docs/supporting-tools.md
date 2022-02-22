---
layout: default
title: Supporting tools
nav_order: 4
---

# Supporting tools and services

{: .no_toc }


A `devcontainer.json` file in your project tells tools and services that support the dev container spec how to access (or create) a **development container** with a well-defined tool and runtime stack. 

This page outlines tools and services that currently support this format.

While most [dev container properties](json-reference.md) apply to any `devcontainer.json` supporting tool or service, a few are specific to certain tools.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


## devcontainer CLI

Given the growing number of use cases for dev containers, there is a companion [devcontainer command line interface](https://code.visualstudio.com/docs/remote/devcontainer-cli) (CLI) that can be used independent of the Remote - Containers extension or GitHub Codespaces.

## GitHub Codespaces

A [codespace](https://docs.github.com/en/codespaces/overview) is a development environment that's hosted in the cloud. Codespaces run on a variety of VM-based compute options hosted by GitHub.com, which you can configure from 2 core machines up to 32 core machines. You can connect to your codespaces from the browser or locally using Visual Studio Code.

> **Tip:** If you've already built a container and connected to it, be sure to run **Codespaces: Rebuild Container** from the Command Palette (`kbstyle(F1)`) to pick up any changes you make.

### Product specific limitations

Some properties may apply differently to Codespaces. Please note that Codespaces supports [VS Code properties](#visual-studio-code-remote---containers).

| Property or variable | Type | Description |
|----------|---------|----------------------|
| `mounts` | array | Codespaces ignores "bind" mounts with the exception of the Docker socket. Volume mounts are still allowed.|
| `workspaceMount` | string | Not yet supported in Codespaces. |
| `workspaceFolder` | string | Not yet supported in Codespaces. |
| `forwardPorts` | array | Codespaces does not yet support the `"host:port"` variation of this property. |
| `portsAttributes` | object | Codespaces does not yet support the `"host:port"` variation of this property.|
| `shutdownAction` | enum | Does not apply to Codespaces. |
| `${localEnv:VARIABLE_NAME}` | Any | For Codespaces, the host is in the cloud rather than your local machine.|

## Visual Studio Code Remote - Containers

The [**Visual Studio Code Remote - Containers** extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) lets you use a [Docker container](https://docker.com) as a full-featured development environment. It allows you to open any folder inside (or mounted into) a container and take advantage of Visual Studio Code's full feature set. There is more information in the Remote - Containers [documentation](https://code.visualstudio.com/docs/remote/containers).

> **Tip:** If you've already built a container and connected to it, be sure to run **Remote-Containers: Rebuild Container** from the Command Palette (`kbstyle(F1)`) to pick up any changes you make.

### Product specific properties

Some properties are specific to VS Code. Please note that Codespaces supports the VS Code properties.

| Property | Type | Description |
|----------|------|-------------|
| `extensions` | array | An array of extension IDs that specify the extensions that should be installed inside the container when it is created. Defaults to `[]`. |
| `settings` | object | Adds default `settings.json` values into a container/machine specific settings file. Defaults to `{}`. |

### Product specific limitations

Some properties may also have certain limitations in the Remote - Containers extension.

| Property or variable | Type | Description |
|----------|------|-------------|
| `workspaceMount` | string | Not yet supported when using Clone Repository in Container Volume. |
| `workspaceFolder` | string | Not yet supported when using Clone Repository in Container Volume. |
| `${localWorkspaceFolder}`  | Any | Not yet supported when using Clone Repository in Container Volume. |
| `${localWorkspaceFolderBasename}` | Any | Not yet supported when using Clone Repository in Container Volume. |

## Schema

You can see the VS Code implementation of the dev container schema [here](https://github.com/microsoft/vscode/blob/main/extensions/configuration-editing/schemas/devContainer.schema.src.json).