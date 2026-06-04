[← back to README](../README.md)

# corporate / team & productivity

## 17. slack

messages, channel history, posting.

- **install:** the original anthropic reference server was archived and is now maintained by zencoder as `@zencoderai/slack-mcp-server` (npx, with slack bot/app tokens in env). check the repo for the current token setup.
- **link:** https://github.com/zencoderai/slack-mcp-server
- **gotcha:** an official slack-hosted remote endpoint couldn't be confirmed, so use the maintained community server rather than a guessed url. posting to channels is a side effect with an audience — confirm before the agent sends anything human-visible.

## 18. linear

issues, sprint planning, search. official remote server.

- **install:** add the remote server and complete oauth; linear's docs page has the current endpoint and one-click setup for each client
- **link:** https://linear.app/docs/mcp
- **gotcha:** permissions inherit your linear access. the agent can do what you can do.

## 19. notion

pages and databases. official hosted server (makenotion), replaced the community forks.

- **install:** `claude mcp add --transport http notion https://mcp.notion.com/sse` then complete oauth
- **link:** https://developers.notion.com/guides/mcp/mcp
- **gotcha:** scope the integration to the workspaces you want reachable, not everything. notion is prioritizing the remote server and may sunset the local one.

## 20. jira / confluence (atlassian rovo)

issues, confluence docs, compass. official atlassian rovo remote server covers all of them.

- **install:** `claude mcp add --transport http atlassian https://mcp.atlassian.com/v1/mcp/authv2` then complete oauth
- **link:** https://www.atlassian.com/platform/remote-mcp-server
- **gotcha:** the older `/v1/sse` endpoint stops working after june 30, 2026 — use the `/mcp` endpoint above. oauth 2.1, respects your existing access controls.

## 21. google drive

file search and read across your drive.

- **install:** `claude mcp add gdrive npx @modelcontextprotocol/server-gdrive`
- **link:** https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gdrive
- **gotcha:** this reference server was archived too — it works but isn't maintained. oauth scope decides what it can see. grant read-only and a specific folder where you can.

## 22. gmail

read and send mail.

- **install:** community server via npx, oauth on first call
- **link:** https://github.com/GongRzhe/Gmail-MCP-Server
- **gotcha:** send is a side effect that leaves your account. never let an agent send mail unsupervised. community-maintained — vet it.

## 23. google calendar

events, scheduling, availability checks.

- **install:** community server via npx, oauth on first call
- **link:** https://github.com/nspady/google-calendar-mcp
- **gotcha:** creating invites notifies real people. confirm before it writes.

## 24. asana

tasks, projects, workload. official v2 remote server (went GA early 2026).

- **install:** `claude mcp add --transport http asana https://mcp.asana.com/v2/mcp` then complete oauth
- **link:** https://developers.asana.com/docs/using-asanas-mcp-server
- **gotcha:** don't use the old `/sse` beta endpoint — it was deprecated and shut down may 2026. inherits your asana permissions.

## 25. airtable

records, bases, schema.

- **install:** `claude mcp add airtable npx airtable-mcp-server` (api key in env)
- **link:** https://github.com/domdomegg/airtable-mcp-server
- **gotcha:** community-maintained, well regarded. scope the pat to specific bases.
