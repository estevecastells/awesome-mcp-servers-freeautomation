# Invokely MCP Connector

Invokely's MCP connector is a local stdio adapter for the hosted Invokely statistics service. The connector forwards tool definitions and results; the hosted service implementation is not included in the connector repository.

## Requirements

- Node.js 22 or later
- An MCP client that can launch a local stdio process

## Installation

Clone the connector repository and install its dependencies:

```sh
git clone https://github.com/estevecastells/invokely-mcp-connector.git
cd invokely-mcp-connector
npm install
```

The connector is not published to the npm registry. Launch it from the checkout using Node and the absolute paths for your installation:

```json
{
  "mcpServers": {
    "invokely": {
      "command": "/absolute/path/to/node",
      "args": ["/absolute/path/to/invokely-mcp-connector/src/cli.mjs"]
    }
  }
}
```

With no API key, the connector uses Invokely's anonymous trial endpoint, limited to 25 calls per day per IP address. The Free plan includes 500 MCP calls per month. An API key is optional; configure `INVOKELY_API_KEY` in the MCP client's local environment or secret settings to use bearer authentication. The connector reads the key from its environment for the request and does not persist it. Do not put a real key in a shared configuration file.

## Tools

The connector forwards the tools and schemas returned by Invokely's hosted MCP service. The current service lists six statistics tools: `search_indicators`, `resolve_place`, `get_value`, `get_series`, `compare`, and `rank_places`. It also lists five workspace tools: `workspace_list`, `workspace_get`, `workspace_save`, `workspace_update`, and `workspace_delete`. Private workspace access is a Pro feature. Workspace deletion is irreversible, so review the service documentation and confirm before using that operation.

Statistics results include source citations. Invokely's developer documentation describes the service and current tool behavior; its pricing page has current plan details.

- [Invokely developer documentation](https://invokely.ai/docs)
- [Invokely pricing](https://invokely.ai/pricing)
- [Connector source and license](https://github.com/estevecastells/invokely-mcp-connector)

The connector repository is MIT-licensed. That license applies to the local connector source, not to Invokely's hosted backend or service.
