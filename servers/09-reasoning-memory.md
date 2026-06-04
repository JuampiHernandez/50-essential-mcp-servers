[← back to README](../README.md)

# the reasoning & memory layer

these don't connect to an external service — they make the agent itself work better. worth knowing.

## 49. sequential thinking

forces the agent to break a complex problem into ordered, explicit steps. useful for architecture decisions, big refactors, anything with a tangle of dependencies. anthropic reference server.

- **install:** `claude mcp add sequential-thinking npx @modelcontextprotocol/server-sequential-thinking`
- **link:** https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking
- **gotcha:** pure reasoning aid, zero external access. costs only tokens. (still actively maintained in the main reference repo.)

## 50. memory

persistent memory across conversations — the agent keeps a knowledge graph of entities and relationships so it remembers context between sessions. official anthropic server, stored locally.

- **install:** `claude mcp add memory npx @modelcontextprotocol/server-memory`
- **link:** https://github.com/modelcontextprotocol/servers/tree/main/src/memory
- **gotcha:** the data lives locally. it's only as private as the machine it's on.
