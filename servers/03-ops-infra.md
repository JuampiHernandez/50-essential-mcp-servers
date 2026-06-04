[← back to README](../README.md)

# ops, infra & cloud

## 11. cloudflare

workers, dns, r2, kv, zero trust — the whole api. the main server covers 2,500+ endpoints through two tools (search/execute) using ~1k tokens instead of leaking the whole spec.

- **install:** add `{"url": "https://mcp.cloudflare.com/mcp"}` to your config; connect and you're redirected to cloudflare to authorize and pick permissions
- **link:** https://github.com/cloudflare/mcp
- **gotcha:** cloudflare also ships product-specific servers (docs, observability, dns analytics). use the focused one if you only need a slice.

## 12. vercel

deploys, env vars, log inspection. official.

- **install:** `claude mcp add --transport http vercel https://mcp.vercel.com`
- **link:** https://vercel.com/docs/mcp
- **gotcha:** deploy and env-var changes are real side effects. keep a human in the loop on anything that ships.

## 13. aws

ec2, s3, lambda, rds via natural language.

- **install:** aws publishes per-service MCP servers; install the ones you need from the awslabs repo
- **link:** https://github.com/awslabs/mcp
- **gotcha:** iam scope is everything here. give the agent a tightly-scoped role, not your admin keys.

## 14. docker hub

image search, tag management — useful if you live in containers.

- **install:** `claude mcp add docker npx mcp-server-docker`
- **link:** https://hub.docker.com
- **gotcha:** community-maintained. read the source before granting it anything beyond read.

## 15. sentry

issues, stack traces, event detail piped straight into the agent. the github + sentry combo is the killer one — read a prod error, propose a PR.

- **install:** `claude mcp add --transport http sentry https://mcp.sentry.dev/mcp`
- **link:** https://docs.sentry.io/product/sentry-mcp/
- **gotcha:** stack traces and breadcrumbs can carry sensitive data. mind what you're feeding the model.

## 16. kubernetes

cluster inspection and kubectl-style ops in plain english.

- **install:** `claude mcp add kubernetes npx mcp-server-kubernetes`
- **link:** https://github.com/Flux159/mcp-server-kubernetes
- **gotcha:** community-maintained. point it at a non-prod context first. an agent with cluster write access is a bad day waiting to happen.
