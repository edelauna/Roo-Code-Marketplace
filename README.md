# Roo-Code Package Manager Template

This repository serves as a template for creating package manager items for Roo-Code. It demonstrates different repository organization patterns and contains examples of various package manager items.

## Repository Organization Patterns

There are three main patterns for organizing a package manager repository:

### 1. Simple Single-Item Pattern
Best for small repositories with independent items.

```
simple-items/
├── modes/
│   ├── developer-mode/
│   │   ├── metadata.en.yml
│   │   └── mode.md
│   └── architect-mode/
│       ├── metadata.en.yml
│       └── mode.md
├── mcp-servers/
│   └── file-analyzer/
│       ├── metadata.en.yml
│       └── server.js
└── metadata.en.yml
```

**Pros:**
- Simple and straightforward organization
- Easy to maintain
- Clear item independence
- Quick to browse and understand

**Cons:**
- Can become cluttered with many items
- No built-in grouping for related items
- Limited organization options

### 2. Grouped Items Pattern
Best for large repositories with many items that benefit from logical grouping.

```
grouped-items/
├── data-engineering/
│   ├── modes/
│   │   ├── data-engineer-mode/
│   │   │   ├── metadata.en.yml
│   │   │   ├── metadata.es.yml
│   │   │   └── mode.md
│   │   └── data-architect-mode/
│   │       ├── metadata.en.yml
│   │       └── mode.md
│   └── mcp-servers/
│       └── data-processor/
│           ├── metadata.en.yml
│           ├── metadata.ja.yml
│           └── server.js
├── web-development/
│   ├── modes/
│   │   └── web-developer-mode/
│   │       ├── metadata.en.yml
│   │       └── mode.md
│   └── mcp-servers/
│       └── api-tester/
│           ├── metadata.en.yml
│           └── server.js
└── metadata.en.yml
```

**Pros:**
- Better organization for large collections
- Logical grouping of related items
- Easier to maintain focused collections
- Better discoverability through group context

**Cons:**
- More complex structure
- Requires planning for group organization
- May need occasional restructuring as collection grows

### 3. Package Pattern
Best for items that work together as a unit.

```
packages/
├── data-platform/
│   ├── metadata.en.yml      # Required English metadata
│   ├── metadata.es.yml      # Optional Spanish metadata
│   ├── metadata.ja.yml      # Optional Japanese metadata
│   ├── modes/
│   │   ├── platform-admin-mode/
│   │   │   ├── metadata.en.yml
│   │   │   └── mode.md
│   │   └── platform-user-mode/
│   │       ├── metadata.en.yml
│   │       └── mode.md
│   └── mcp-servers/
│       └── data-validator/
│           ├── metadata.en.yml
│           └── server.js
└── metadata.en.yml
```

**Pros:**
- Perfect for interdependent components
- Single installation unit
- Ensures version compatibility
- Clear documentation of relationships

**Cons:**
- More complex metadata management
- All-or-nothing installation
- May include unnecessary components
- More complex updates

## Metadata Configuration

> Note: The `author` field is automatically populated from git history at runtime and should not be included in metadata files.

### Root Metadata (metadata.en.yml)
```yaml
name: "Example Package Manager Repository"
description: "A collection of example package manager items for Roo-Code"
version: "1.0.0"
tags: ["example", "template"]
```

### Item Metadata (metadata.en.yml)
```yaml
name: "Component Name"
description: "Detailed description of the component"
type: "mode|mcp server|prompt|package"
version: "1.0.0"
tags: ["tag1", "tag2"]
sourceUrl: "https://github.com/username/repo"  # Optional
```

### Package Metadata
By convention, all components in a package's subfolders are automatically included as part of the package. The `items` array is only needed when referencing components that exist outside the package's folder structure.

Standard package metadata (metadata.en.yml):
```yaml
name: "Package Name"
description: "Package description"
type: "package"
version: "1.0.0"
tags: ["package", "tag2"]
```

Package metadata with external references:
```yaml
name: "Extended Package"
description: "Package that includes external components"
type: "package"
version: "1.0.0"
tags: ["package", "extended"]
items:
  - type: "mode"
    path: "../shared-modes/admin-mode"  # Reference to a mode outside the package
  - type: "mcp server"
    path: "../../global-servers/validator"  # Reference to a server in parent directory
```

## Localization Support

All metadata files must include a locale identifier in their filename. The English locale (`.en.yml`) is required as it serves as the fallback when a user's locale is not available. If an English metadata file is not present, the item will not be loaded.

Example directory structure with localized metadata:
```
component/
├── metadata.en.yml  # Required English metadata (fallback)
├── metadata.es.yml  # Spanish metadata
├── metadata.ja.yml  # Japanese metadata
└── component.js
```

Example localized metadata files:
```yaml
# metadata.en.yml (required)
name: "Data Processor"
description: "Processes data files efficiently"
type: "mcp server"
version: "1.0.0"
tags: ["processing", "data"]

# metadata.es.yml (optional)
name: "Procesador de Datos"
description: "Procesa archivos de datos de manera eficiente"
type: "mcp server"
version: "1.0.0"
tags: ["procesamiento", "datos"]

# metadata.ja.yml (optional)
name: "データプロセッサー"
description: "データファイルを効率的に処理"
type: "mcp server"
version: "1.0.0"
tags: ["処理", "データ"]
```

Note: The English metadata file (`.en.yml`) is required and serves as the fallback. Other localizations are optional but must maintain the same structure and version as the English file.

## Testing

To test this repository with the Roo-Code Package Manager:

1. Create a new GitHub repository
2. Upload this template to the repository
3. In Roo-Code, go to the Package Manager tab
4. Click on the "Sources" tab
5. Add your repository URL
6. Go back to the "Browse" tab to see your package manager items

## Examples

This template includes examples of all three organization patterns:

1. Simple items in the root `/modes` and `/mcp-servers` directories
2. Grouped items in the `/groups` directory
3. Package examples in the `/packages` directory

Each example includes proper metadata configuration and demonstrates best practices for its pattern.