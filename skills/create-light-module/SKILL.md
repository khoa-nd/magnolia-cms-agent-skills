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

<!-- Describe what this skill does and when Claude should use it -->

This skill helps create Magnolia CMS light modules with the proper folder structure and configuration files.

## When to Use

Use this skill when the user wants to:

- Create a new Magnolia light module
- Set up the folder structure for a light module
- Generate light module configuration files

## Instructions

<!-- Add detailed instructions for how Claude should execute this skill -->

### Prerequisites

- Magnolia CMS environment set up
- Access to the light-modules directory

### Steps

1. Determine the light module name
2. Create the required folder structure
3. Generate necessary configuration files

### Folder Structure

```
<module-name>/
├── decorations/
├── dialogs/
├── i18n/
├── includes/
├── templates/
│   ├── components/
│   └── pages/
├── webresources/
│   ├── css/
│   ├── js/
│   └── images/
└── <module-name>.yaml
```

## Examples

<!-- Add example prompts and expected behavior -->

**User prompt:** "Create a new light module called my-website"

**Expected behavior:** Claude creates the complete folder structure with all necessary files for a Magnolia light module named "my-website".

## Notes

<!-- Any additional notes, limitations, or considerations -->

- Light modules must be placed in the `light-modules` directory of your Magnolia installation
- Module names should be lowercase with hyphens (kebab-case)
