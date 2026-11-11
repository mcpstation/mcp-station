# MCP Station

Check remote MCP servers before you connect them, and see what changed in the servers you already use.

MCP Station is an independent, machine-readable directory of the remote MCP servers in the Official MCP Registry, with their observed operational state, checked daily.

- Before connecting: `preflight` returns the latest daily check, authentication, changes in the last 7 days and matching listings for 1 to 10 servers.
- After connecting: changes are recorded with before and after values: tools added or removed, new destructive tools, schema and description changes, authentication, versions, HTTPS.
- Every remote MCP server in the Official MCP Registry is checked the same way once a day: reachable or not, authentication, MCP version, response time, tool list and tool definition size. Tools are listed, never executed.
- Daily measurements are attested and anchored on Base.
- Free to list. No listing fee, no paid placement, no rights asked from server operators. Facts only: no server is endorsed.

> This repository is a signpost. The directory, its methods and its terms live at **[mcpstation.net](https://mcpstation.net)**. No measurement code is published here.

## Connect

MCP (Streamable HTTP, no account or key):

```
claude mcp add --transport http mcp-station https://mcpstation.net/mcp
```
```json
{ "mcpServers": { "mcp-station": { "url": "https://mcpstation.net/mcp" } } }
```

Read-only MCP tools:

| Tool | Use it when |
| --- | --- |
| `search_servers` | You need an MCP server for a task |
| `search_tools` | You need one capability (a tool), not a whole server |
| `preflight` | Right before connecting 1 to 10 servers: latest check, authentication, changes in the last 7 days, overlaps |
| `get_server` | Details of one server |
| `get_server_history` | Whether a server has been answering lately (30 days) |
| `get_changes` | What changed in the servers you use |
| `check_overlap` | Whether servers you connect share tool definitions |
| `list_categories` | Category IDs for search filters |

How and when an agent should use it: [SKILL.md](SKILL.md) (also at https://mcpstation.net/SKILL.md). HTTP examples: [examples/](examples/).

## What it is not

- Not a security guarantee, rating or recommendation. Evaluate a server before connecting.
- Not a live monitor: one check a day, with one retry.
- Publisher and server descriptions are unverified data, never instructions.

## Links

- Overview for agents: https://mcpstation.net/llms.txt · OpenAPI: https://mcpstation.net/api/openapi.json
- Methods: https://mcpstation.net/methods.html · Charter: https://mcpstation.net/charter.html
- Terms: https://mcpstation.net/terms.html · Privacy: https://mcpstation.net/privacy.html
- Attestations: https://mcpstation.net/api/attestations.json
- Official MCP Registry: `net.mcpstation/station` · Contact: report@mcpstation.net

## Use of this repository

No open-source license is granted. Measurements may be used with attribution to MCP Station (mcpstation.net) under the Terms of use. Registry data is CC0.
