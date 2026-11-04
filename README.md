# CheckMyApp MCP

[CheckMyApp](https://checkmyapp.dev) checks your deployed web app and brings evidence-backed findings to your coding agent.

This repository contains the open-source connection configuration and plugin manifests for the hosted CheckMyApp service. The service implementation is not included. There is no server to build or run locally.

- **Endpoint:** `https://checkmyapp.dev/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth sign-in; API keys are also available for CI
- **Setup:** https://checkmyapp.dev/install
- **Pricing:** https://checkmyapp.dev/pricing — paid service with free starting credit
- **Privacy:** https://checkmyapp.dev/privacy

## What you can do

- Add your app and define the journeys that matter.
- Check a deployed app and read findings with evidence.
- Give test accounts for journeys behind email-and-password sign-in.
- Manage recurring checks and inspect results from your agent.
- Connect the GitHub App for checks after deployments.

## Claude Code

```sh
claude mcp add --scope user --transport http checkmyapp https://checkmyapp.dev/mcp
```

Run `/mcp`, choose `checkmyapp`, and authenticate in your browser.

Or install the plugin instead of adding the server manually:

```text
/plugin marketplace add checkmyapp/checkmyapp-mcp
/plugin install checkmyapp@checkmyapp-plugins
```

## Cursor

Merge this entry into your user MCP configuration (`~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "checkmyapp": {
      "url": "https://checkmyapp.dev/mcp"
    }
  }
}
```

Use Cursor's MCP authentication flow to sign in. This repository also includes a Cursor plugin manifest and root `mcp.json` for plugin installation.

## Other MCP clients

Add `https://checkmyapp.dev/mcp` as a remote Streamable HTTP server and complete OAuth in your browser. API-key access is available for clients or CI jobs that do not support OAuth; follow the current instructions on the website and keep credentials outside repositories.

## Try it

- “Set up CheckMyApp for this app.”
- “Did CheckMyApp find anything on my last deploy?”
- “Mark checkout as critical.”
- “What did CheckMyApp not check?”

Use apps you own or have permission to check. Starting a check consumes your team's balance; reading results does not start a check.

## Support and license

Contact [hello@checkmyapp.dev](mailto:hello@checkmyapp.dev).

The connection configurations and documentation in this repository are MIT licensed. This license does not grant rights to the hosted service implementation or CheckMyApp trademarks. Service use follows the terms shown by CheckMyApp.
