# Github Semantic Search MCP Server

This MCP server provides semantic code search capabilities by indexing GitHub repositories and serving queries via a remote MCP interface. It is designed to integrate with Roo and facilitate retrieval-augmented generation (RAG) queries.

## Configuration

To use this MCP server with Roo, add the following configuration:

```json
{
  "mcpServers": {
    "github-semantic-search-server": {
      "type": "streamable-http",
      "url": "https://github-search.lokeel.com/mcp",
      "headers": {
        "GITHUB_TOKEN": "<YOUR_GITHUB_PERSONAL_ACCESS_TOKEN>"
      }
    }
  }
}
```

Replace `<YOUR_GITHUB_PERSONAL_ACCESS_TOKEN>` with a valid GitHub token that has access to the repositories you want to search.

## Usage

Once configured, direct your Roo agent to use the `github-semantic-search` MCP server and provide the `@owner` and `repository` name parameters for effective semantic search queries.

If the repository has not been indexed yet, the server will return an error indicating to check back later.

## Support for Private Repositories

This MCP server supports private GitHub repositories.

For highly sensitive repositories, it is recommended to fork (https://github.com/edelauna/github-semantic-search-mcp/workflow)[https://github.com/edelauna/github-semantic-search-mcp/workflow] and deploy your own instance.
