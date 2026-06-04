# contributing

this list is a snapshot of a fast-moving ecosystem. MCP servers get archived, replaced, re-hosted, and re-authed on a near-weekly basis — an endpoint that was correct last month can be dead today. that's exactly why corrections are welcome.

## what makes a good PR

- **verify install strings against official docs first.** before you change or add a command, confirm it against the vendor's own repo or documentation. the whole value of this list is that the install strings are trustworthy — don't paste a command you haven't checked.
- **fix stale endpoints.** if a hosted url moved, an `/sse` endpoint got deprecated, or a package was renamed, open a PR with a link to the official source that confirms the new one.
- **flag archived or unmaintained servers.** if a server has been archived or handed off to a new maintainer, note it — and keep the existing `community-maintained`, `archived`, and money/irreversibility warnings intact. those warnings are accuracy-critical; don't soften or drop them.
- **don't invent.** no servers, install commands, or links that you can't point to in official docs. where a vendor only documents "check our docs" rather than a copy-paste command, keep it that way.

## what to include

a server entry keeps four things: a one-line description, the install command (or "check vendor docs"), the official link, and the gotcha. match the existing format and the lowercase house style.

## the spirit of it

this is a menu, not a shopping spree — the list stays curated and opinionated, not exhaustive. a sharp, verified entry beats five vague ones. if in doubt, link the source and let the reviewer check.

thanks for helping keep it accurate.
