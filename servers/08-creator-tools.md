[← back to README](../README.md)

# creator tools — media & design

## 41. higgsfield

official server, launched april 2026 — 30+ image and video models (sora, veo, kling, seedance) through one endpoint. research, prompt-optimize, generate ads/videos/brand content. for paid creative work this is the missing layer between a prompt and a finished asset.

- **install:** connect via the official higgsfield connector / hosted endpoint with your account credits
- **link:** https://higgsfield.ai
- **gotcha:** there are community "unlimited" forks that scrape your logged-in session via browser cookies. skip those — they break constantly and you're handing your session to a third party. use the official connector.

## 42. davinci resolve

control resolve studio through its scripting api — timeline edits, media pool organization, render setup, color grading, fusion, fairlight. genuinely powerful for an editing workflow.

- **install:** clone `samuelgursky/davinci-resolve-mcp` (npm launcher auto-configures claude/cursor/codex), or `apvlv/davinci-resolve-mcp` via uv
- **link:** https://github.com/samuelgursky/davinci-resolve-mcp
- **gotcha:** community-maintained (two main forks). requires resolve studio open with preferences → general → external scripting set to "local" before it connects.

## 43. figma

official dev mode server. read components, variables, layout; generate code from frames; with the newer write-to-canvas feature the agent can create and update native figma content too.

- **install:** enable the desktop server in figma (dev mode → enable mcp), then `claude mcp add --transport http figma-desktop http://127.0.0.1:3845/mcp` — or use the remote server, which has the broadest features
- **link:** https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server
- **gotcha:** remote vs desktop matters — remote is what most people want; desktop is for specific enterprise cases and runs locally on port 3845.

## 44. elevenlabs

official text-to-speech and audio server — generate speech, clone voices, transcribe. free tier with 10k credits/month.

- **install:** add `elevenlabs` as a `uvx elevenlabs-mcp` command block with `ELEVENLABS_API_KEY` in env (claude desktop: Settings → Developer → Edit Config)
- **link:** https://github.com/elevenlabs/elevenlabs-mcp
- **gotcha:** needs uv installed. on windows you have to enable developer mode in claude desktop. voice cloning has obvious consent implications — only clone voices you're allowed to.

## 45. blender

drive blender's 3d engine — create scenes, objects, materials, lighting from prompts.

- **install:** community server, requires blender installed + an addon bridge
- **link:** https://github.com/ahujasid/blender-mcp
- **gotcha:** community-maintained, medium setup difficulty. needs blender open with the companion addon running.

## 46. canva

generate and edit designs from templates.

- **install:** `claude mcp add --transport http canva https://mcp.canva.com/mcp`
- **link:** https://www.canva.dev/docs/apps/mcp-server/
- **gotcha:** oauth on first call. inherits your canva account access.

## 47. ableton live

control ableton — create tracks, midi, devices, manipulate a live set.

- **install:** community server, requires ableton + a remote-script bridge
- **link:** https://github.com/ahujasid/ableton-mcp
- **gotcha:** community-maintained, niche, fiddly setup. fun for music production experiments, not production-critical.

## 48. youtube

video search and transcript extraction — great for research and repurposing content.

- **install:** `claude mcp add youtube npx @anaisbetts/mcp-youtube`
- **link:** https://github.com/anaisbetts/mcp-youtube
- **gotcha:** community-maintained. transcript availability depends on the video having captions.
