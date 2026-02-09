---
name: create-light-module
description: Create Magnolia CMS light modules with proper folder structure and configuration files.
metadata:
  author: khoanguyen
  version: "1.0"
---

# create-light-module

> A skill for creating Magnolia CMS light modules

## Description

This skill helps create Magnolia CMS light modules with the proper folder structure and configuration files. A light module is a directory on the file system that contains YAML definition files, FreeMarker template scripts, and other resource files - enabling file-based configuration instead of JCR storage.

Light modules allow front-end developers to create Magnolia projects without Java expertise, making templates easier to understand, merge, and version control.

## When to Use

Use this skill when the user wants to:

- Create a new Magnolia light module
- Set up the folder structure for a light module
- Generate light module configuration files (module.yaml, i18n properties)
- Scaffold page templates, component templates, or dialogs
- Create apps, content types, or REST endpoints in a light module

## Instructions

### Prerequisites

- Magnolia CMS environment set up
- Access to the `light-modules` directory
- (Optional) Magnolia CLI installed for scaffolding: `npm install @anthropic/magnolia-cli`

### CLI Command (if using Magnolia CLI)

```bash
mgnl create-light-module <name> [options]
```

#### CLI Options

| Option | Description |
|--------|-------------|
| `-d, --directories` | Create specific directories (A=apps, B=blocks, C=contentTypes, D=decorations, E=dialogs, I=includes, M=messageViews, R=restEndpoints, T=templates, H=themes, V=virtualUriMappings, W=webresources) |
| `-md, --module-descriptor` | Specify module version (default: 1.0.0) |
| `-lmp, --light-modules-path` | Set directory path for the new light module |
| `-p, --prototype` | Select a prototype: `_default` (frequently used folders) or `comprehensive` (complete structure) |

### Manual Creation Steps

1. Determine the light module name (use kebab-case)
2. Create the required folder structure
3. Generate the `module.yaml` descriptor file
4. Create i18n properties file for internationalization
5. Add README.md for documentation

### Folder Structure

#### Default Structure

```
<module-name>/
├── README.md
├── module.yaml
├── i18n/
│   └── <module-name>-messages_en.properties
├── dialogs/
│   └── components/
│   └── pages/
├── templates/
│   ├── components/
│   └── pages/
└── webresources/
    ├── css/
    ├── js/
    └── images/
```

#### Comprehensive Structure

```
<module-name>/
├── README.md
├── module.yaml
├── apps/
├── blocks/
├── contentTypes/
├── decorations/
├── dialogs/
│   ├── components/
│   └── pages/
├── i18n/
│   └── <module-name>-messages_en.properties
├── includes/
├── messageViews/
├── restEndpoints/
├── templates/
│   ├── components/
│   └── pages/
├── themes/
├── virtualUriMappings/
└── webresources/
    ├── css/
    ├── js/
    └── images/
```

### Core Files

#### module.yaml

```yaml
name: <module-name>
version: 1.0.0
```

#### Page Template Definition (templates/pages/home.yaml)

```yaml
renderType: freemarker
templateScript: /<module-name>/templates/pages/home.ftl
dialog: <module-name>:pages/homePageProperties
title: Home Page
areas:
  main:
    availableComponents:
      text:
        id: <module-name>:components/text
```

#### Component Template Definition (templates/components/text.yaml)

```yaml
renderType: freemarker
templateScript: /<module-name>/templates/components/text.ftl
dialog: <module-name>:components/textDialog
title: Text Component
```

#### Dialog Definition (dialogs/components/textDialog.yaml)

```yaml
form:
  properties:
    text:
      $type: richTextField
      label: Text Content
```

#### i18n Properties (<module-name>-messages_en.properties)

```properties
<module-name>.pages.home.title=Home Page
<module-name>.components.text.title=Text Component
```

## Supported Definition Types

Light modules support these file-based definitions:

| Type | Directory | Description |
|------|-----------|-------------|
| Apps | `apps/` | Content apps with data sources and workbench |
| Blocks | `blocks/` | Reusable content blocks |
| Content Types | `contentTypes/` | Define content structure |
| Decorations | `decorations/` | Decorate existing definitions |
| Dialogs | `dialogs/` | Editor UI forms |
| Includes | `includes/` | Reusable FreeMarker includes |
| Message Views | `messageViews/` | Custom message templates |
| REST Endpoints | `restEndpoints/` | REST API definitions |
| Templates | `templates/` | Page and component templates |
| Themes | `themes/` | Visual themes |
| Virtual URI Mappings | `virtualUriMappings/` | URL rewriting rules |
| Web Resources | `webresources/` | Static assets (CSS, JS, images) |

## Examples

**User prompt:** "Create a new light module called my-website"

**Expected behavior:** Claude creates the complete folder structure with:
- `my-website/module.yaml` with version 1.0.0
- `my-website/README.md` with module documentation
- `my-website/i18n/my-website-messages_en.properties`
- Standard directories: `templates/`, `dialogs/`, `webresources/`

**User prompt:** "Create a comprehensive light module called corporate-site with all directories"

**Expected behavior:** Claude creates the full folder structure including apps, blocks, contentTypes, decorations, dialogs, includes, messageViews, restEndpoints, templates, themes, virtualUriMappings, and webresources.

**User prompt:** "Add a home page template to my-website light module"

**Expected behavior:** Claude creates:
- `templates/pages/home.yaml` - Template definition
- `templates/pages/home.ftl` - FreeMarker template script
- `dialogs/pages/homePageProperties.yaml` - Page properties dialog

## Notes

- Light modules must be placed in the `light-modules` directory of your Magnolia installation
- Module names should be lowercase with hyphens (kebab-case)
- Use `.yaml` extension (not `.yml`) for all definition files
- Magnolia auto-detects file changes without restart (hot-reload)
- Light modules can be converted to Maven modules by copying contents

### Limitations

Light modules do **not** support:
- Workspace registration
- Node type registration
- Module classes (Java)
- Version handlers
- Workflows

For these features, use traditional Maven/Java modules.

## References

- [Magnolia CLI Create Light Module Plugin](https://docs.magnolia-cms.com/magnolia-cli/plugins/available-plugins/create-light-module-plugin/)
- [Light Development in Magnolia](https://docs.magnolia-cms.com/product-docs/developing/light-development-in-magnolia/)
