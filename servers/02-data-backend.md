[← back to README](../README.md)

# databases & backend

## 6. postgres

direct sql against your database — schema-aware debugging, data-shape checks before you write a migration.

- **install:** `claude mcp add postgres npx @modelcontextprotocol/server-postgres "postgresql://user:pass@localhost:5432/db"`
- **link:** https://github.com/modelcontextprotocol/servers-archived/tree/main/src/postgres
- **gotcha:** heads up — anthropic's reference postgres server was archived. the npm package still installs and works, but it's unmaintained. for anything serious in 2026, use your provider's official server (supabase/neon below) or `@bytebase/dbhub`, which claude's own docs now point to. read-only by default. never point it at prod writes.

## 7. supabase

your whole backend through chat — database, auth, storage, edge functions. official, actively maintained.

- **install:** `claude mcp add --transport http supabase https://mcp.supabase.com/mcp`
- **link:** https://github.com/supabase-community/supabase-mcp
- **gotcha:** start in read-only mode. it ships with that default for a reason — flip writes on only once you trust the loop.

## 8. neon

serverless postgres with a killer feature: branch-based migrations. when the agent runs a migration it spins up an instant copy-on-write branch off prod data, tests there, then applies. official.

- **install:** `claude mcp add --transport http neon https://mcp.neon.tech/mcp`
- **link:** https://github.com/neondatabase/mcp-server-neon
- **gotcha:** neon went all-in on the hosted remote server — the local npm package and stdio cli were removed in early 2026. use the url.

## 9. sqlite

local sql against a `.db` file. perfect for poking at datasets or debugging embedded storage.

- **install:** `claude mcp add sqlite npx mcp-server-sqlite-npx /path/to/db.sqlite`
- **link:** https://github.com/johnnyoshika/mcp-server-sqlite-npx
- **gotcha:** the anthropic reference sqlite server was archived too. `mcp-server-sqlite-npx` is the maintained community replacement most setups use now.

## 10. redis

inspect keys, manage caches, monitor memory — without memorizing redis cli. official, from redis themselves.

- **install:** clone `redis/mcp-redis`, run via uv with your redis url in env
- **link:** https://github.com/redis/mcp-redis
- **gotcha:** lock it down with a redis acl read-only user before you connect an agent.
