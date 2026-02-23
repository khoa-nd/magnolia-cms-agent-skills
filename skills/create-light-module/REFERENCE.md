# Magnolia CLI Reference

Curated links to official Magnolia CLI documentation for deeper reference.

## Getting Started

- [Magnolia CLI Overview](https://docs.magnolia-cms.com/magnolia-cli/) — Introduction to the CLI, version comparison (v5 vs v4), and architecture overview.
- [Getting Started](https://docs.magnolia-cms.com/magnolia-cli/getting-started/) — Prerequisites, installation methods (jumpstart, local, global), init command, and first steps.

## Configuration

- [Configuring Plugins](https://docs.magnolia-cms.com/magnolia-cli/plugins/configuring-plugins/) — Structure of `mgnl.config.js`, global and plugin-level properties, logger settings, analytics, and argument precedence.

## Plugin Management

- [Managing Plugins](https://docs.magnolia-cms.com/magnolia-cli/plugins/managing-plugins/) — How to install, uninstall, update, and list CLI plugins using `add-plugin` and npm commands.

## Available Plugins

- [Plugins Overview](https://docs.magnolia-cms.com/magnolia-cli/plugins/) — Complete list of all available plugins with descriptions and example commands.

### Scaffolding Plugins

- [Create Light Module Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-light-module-plugin/) — Scaffold a new light module with folder structure, `module.yaml`, and i18n files. Supports default and comprehensive prototypes.
- [Create Component Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-component-plugin/) — Scaffold components within a light module. Supports making components available on specific page templates.
- [Create Page Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-page-plugin/) — Scaffold page templates with dialog and template files.
- [Create App Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-app-plugin/) — Scaffold content apps with optional content type association.
- [Create Content Type Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-content-type-plugin/) — Scaffold content type definitions with optional associated app and workspace.
- [Create REST Endpoint Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-rest-endpoint-plugin/) — Scaffold REST endpoint YAML configuration files for delivery API. Auto-detects workspaces from content types.
- [Create Block Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-block-plugin/) — Scaffold reusable content blocks with dialog and template. Supports `_default` and `empty` prototypes.
- [Create Virtual URI Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-virtual-uri-plugin/) — Scaffold virtual URI mapping configurations for URL rewriting. Supports `_default`, `regexp`, and `empty` prototypes.

### Operational Plugins

- [Start Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/start-plugin/) — Start a local Magnolia instance and display logs. Requires Java.
- [Jumpstart Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/jumpstart-plugin/) — Bootstrap a new Magnolia project by downloading webapp and setting up project structure.

## Plugin Development

- [Creating Plugins](https://docs.magnolia-cms.com/magnolia-cli/plugins/developing-plugins/creating-plugins/) — Guide to building custom CLI plugins using the `generate-plugin` command. Covers plugin structure, naming conventions, and logger integration.

## Light Development

- [Light Development in Magnolia](https://docs.magnolia-cms.com/product-docs/developing/light-development-in-magnolia/) — Concepts behind light modules, file-based configuration vs JCR, supported definition types, and limitations.
- [Installing Magnolia through npm CLI](https://docs.magnolia-cms.com/product-docs/getting-started-with-magnolia/installing-magnolia/installing-magnolia-through-npm-cli/) — Alternative installation path using npm to download and set up Magnolia CMS.
