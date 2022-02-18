---
layout: default
title: Home
nav_order: 1
description: "An open specification for enriching containers with development specific content and settings."
permalink: /
---

# Development containers
{: .fs-9 }

An open specification for enriching containers with development specific content and settings.
{: .fs-6 .fw-300 }

[View the reference](https://bamurtaugh.github.io/dev-container-spec/docs/json-reference.html){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](https://github.com/microsoft/dev-container-spec){: .btn .fs-5 .mb-4 .mb-md-0 }

---

### What are development containers?

Containers are pieces of software that package code and all of the dependencies that code needs to run, including the runtime, tools, libraries, and settings. Development containers (aka "dev containers") specifically let you code within this piece of software, providing a separate coding environment from your computer.

A `devcontainer.json` file in your project tells your editor how to access (or create) a development container with a well-defined tool and runtime stack. This container can be used to run an application or to separate tools, libraries, or runtimes needed for working with a codebase.

## What is this specification?

As containerizing production workloads becomes commonplace, more developers are using containers for scenarios beyond deployment including continuous integration, test automation, and even full-featured coding environments. Each scenario’s needs can vary between simple single container environments to complex, orchestrated multi-container setups. Rather than attempting to create another orchestrator format, the Development Containers specification seeks to find ways to enrich existing formats with common development specific settings, tools, and configuration while still providing a simplified, un-orchestrated single container option. 

Like the Language Server Protocol before it, the first format in the specification, devcontainer.json, was born out of necessity. It provided a way for tools to add needed configuration to develop inside of local or cloud-based containerized coding. Beyond repeatable setup, these same containers provide consistency to avoid environment specific problems across developers and centralized build and test automation services. The open-source CLI reference implementation can either be used directly or integrated into product experience to deliver these benefits. 

### Resources

Help shape the direction of dev containers and review materials in the [specification repository](https://github.com/microsoft/dev-container-spec).
