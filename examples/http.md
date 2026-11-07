# HTTP examples

```bash
# Find servers: words plus filters (here: no API key, answered at the last check)
curl -s "https://mcpstation.net/api/search?q=crypto+market+data&auth=none&reachable=1&limit=5"

# Find a tool across servers
curl -s "https://mcpstation.net/api/tools/search?q=pdf+table"

# Before connecting: facts for 1 to 10 exact registry names in one call
curl -s "https://mcpstation.net/api/preflight?names=com.example/server-a,com.example/server-b"

# What changed since a date, for the servers you use
curl -s "https://mcpstation.net/api/changes?since=2026-11-01&names=com.example/server-a"

# Daily check history of one server (30 days)
curl -s "https://mcpstation.net/api/history?name=com.example/server-a&days=30"
```

Registry names are exact and case-sensitive. Limits: 60 requests per minute and 3,000 per day per client.
Every answer carries `citation` and `provenance`; cite as "MCP Station (mcpstation.net)".
