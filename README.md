# Roo-Code Marketplace Template

This repository serves as a template for creating marketplace items for Roo-Code. It contains examples of different types of marketplace items and the required structure for each.

## Repository Structure

```
marketplace-template/
├── README.md
├── metadata.yml
├── roles/
│   ├── developer-role/
│   │   ├── metadata.yml
│   │   └── role.md
│   └── architect-role/
│       ├── metadata.yml
│       └── role.md
├── mcp-servers/
│   ├── file-analyzer/
│   │   ├── metadata.yml
│   │   └── server.js
│   └── code-generator/
│       ├── metadata.yml
│       └── server.js
└── storage-systems/
    └── github-storage/
        ├── metadata.yml
        └── storage.js
```

## Root Metadata

The `metadata.yml` file at the root of the repository contains information about the repository itself:

```yaml
name: "Example Marketplace Repository"
description: "A collection of example marketplace items for Roo-Code"
author: "Roo Team"
version: "1.0.0"
lastUpdated: "2025-04-08"
```

## Item Metadata

Each item in the marketplace has its own `metadata.yml` file that contains information about the item:

```yaml
name: "Item Name"
description: "Item description"
type: "role|mcp-server|storage|other"
author: "Author Name"
version: "1.0.0"
lastUpdated: "2025-04-08"
tags: ["tag1", "tag2"]
```

## Testing

To test this repository with the Roo-Code Marketplace:

1. Create a new GitHub repository
2. Upload this template to the repository
3. In Roo-Code, go to the Marketplace tab
4. Click on the "Sources" tab
5. Add your repository URL
6. Go back to the "Browse" tab to see your marketplace items