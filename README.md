# KnowHow plugins

Plugin marketplace and distribution repository for KnowHow Memory.

- `knowhow-memory`: the KnowHow Memory skill and the connection to
  `https://memory.knowhow.app/mcp`. It ships manifests for Claude Code and
  Codex (`.claude-plugin/plugin.json`, `.mcp.json`) and Google Antigravity
  (`plugin.json`, `mcp_config.json`).

The skills in `plugins/*/skills/` are published from `skills/` in
`knowhow-memory` with `just plugins-publish`. Do not edit them here. Edit them
in `knowhow-memory`.
