# Minimal Package Manager Repository

This is a minimal example of a package manager repository structure that meets the basic requirements. The structure is intentionally kept as simple as possible to help diagnose any validation issues.

## Structure

```
/
├── metadata.en.yml         # Required: Repository metadata
└── mcp-servers/           # Optional: Directory for MCP servers
    └── test-server/       
        └── metadata.en.yml
```

## metadata.en.yml
```yaml
name: Test Repository
description: A minimal test repository
version: 1.0.0
```

## mcp-servers/test-server/metadata.en.yml
```yaml
name: Test Server
description: A minimal test server
type: mcp server
version: 1.0.0
```

## Key Points

1. Only metadata.en.yml is strictly required
2. The metadata.en.yml file must have exactly these fields:
   - name (string)
   - description (string)
   - version (in x.x.x format)
3. No quotes around values
4. No extra fields
5. No special characters
6. No complex YAML features (arrays, nested objects, etc.)

Try copying this exact structure to your GitHub repository to test. The validation should pass with this minimal setup.