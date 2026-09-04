# ActivitySmith plugins

MCP-only plugin packages for [ActivitySmith](https://activitysmith.com). Give AI agents access to Push Notifications, Live Activities, Lock Screen Widgets, and remote approvals on iPhone and iPad.

One hosted server provides the tools and OAuth connection. This repository contains distribution metadata and a shared MCP configuration. It has no skills, hooks, local runtime, or copied API implementation.

## Status

Prepared for review. No marketplace submission or acceptance is claimed.

| Client | Package | Distribution |
| --- | --- | --- |
| Cursor | `plugins/activitysmith/.cursor-plugin/plugin.json` | Cursor Marketplace publisher application and review |
| Grok Bot | Cursor package | Cursor connector infrastructure; verify Grok Bot availability during review |
| Grok Build | `plugins/activitysmith/.grok-plugin/plugin.json` | Separate xAI GitHub catalog submission |

See [plugin setup and usage](plugins/activitysmith/README.md), [architecture](docs/architecture.md), and [submission steps](docs/submission.md).

## Layout

```text
.cursor-plugin/marketplace.json
plugins/activitysmith/
  .cursor-plugin/plugin.json
  .grok-plugin/plugin.json
  assets/icon.png
  mcp.json
  README.md
```

Future client manifests can live beside these files and reuse the hosted server. ChatGPT, Codex, and Claude marketplace submissions are outside the current release scope.

## License

MIT covers the files in this repository. Use of the hosted ActivitySmith service is governed by its [terms](https://activitysmith.com/legal/terms-of-service).
