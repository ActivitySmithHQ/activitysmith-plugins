# Distribution design

Reviewed September 4, 2026.

## Recommendation

Ship an MCP-only plugin. Keep the public package small and keep ActivitySmith's capabilities on `https://mcp.activitysmith.com/mcp`.

The backend already implements OAuth, tool discovery, input and output schemas, tool annotations, Push Notifications, Live Activities, widget metrics, and remote approvals. Approval tools already explain the pending-result workflow and the optional MCP Tasks path. A client-side skill would duplicate guidance that the server already supplies.

The MCP server does not currently supply a general `initialize.instructions` field. If fresh-client testing reveals repeated tool-selection mistakes, improve server instructions and tool descriptions first. Add a dedicated server-side workflow tool only when it solves an observed problem. No backend change is required merely to package the current endpoint.

An MCP-only installation makes tools available. It does not make the agent automatically notify the user after every task or require approval for every deployment. Users express those preferences in their prompts or client instructions. Enforced interception would require client-specific hooks or policy integration and is outside this package.

## What to take from Railway

[Railway's repository](https://github.com/railwayapp/railway-skills) puts several client manifests around one plugin directory. Its [Grok Bot integration](https://docs.railway.com/ai/grok-bot-plugin) combines a workflow skill with OAuth access to its hosted MCP server.

Reuse that packaging structure. ActivitySmith does not need Railway's workflow skill or its CLI-oriented operating instructions. The shared MCP configuration is referenced by both manifests so an endpoint edit has one source of truth.

## Marketplace boundaries

[Cursor supports any combination of plugin components](https://cursor.com/docs/plugins), including an MCP server on its own. Skills are optional. Its public submission instructions do not state a Teams or Enterprise subscription requirement. Paid team marketplaces are a separate feature for private distribution. Sign-in and publisher review still apply.

Grok Bot uses Cursor accounts and connector infrastructure. The [official team documentation](https://docs.x.ai/grok-bot/teams-and-enterprises) says it shares Cursor's connector policy and has no separate connector list. [Coolify's first-party plugin repository](https://github.com/coollabsio/coolify-cursor-plugin) also directs publishers to Cursor for both clients. This supports using the Cursor submission route for Grok Bot. Verify the resulting listing in both products; do not assume every Cursor listing becomes available everywhere immediately.

[Grok Build's marketplace](https://github.com/xai-org/plugin-marketplace) is a separate catalog that points to Git repositories at pinned commits. Its `.grok-plugin` manifest in this package is for Grok Build, not evidence of a separate Grok Bot submission requirement.

## Maintenance

Compatible backend changes reach clients without a new plugin download. Clients may cache tool discovery, so a new session or reconnection can still be needed. Endpoint changes, authentication changes, new package assets, and breaking tool changes require a release plan. A pinned package does not pin the implementation of a remote service.

If a skill becomes useful later, keep it limited to a stable workflow. Do not copy the tool catalog, schemas, or endpoint reference into it. Client-managed plugin updates can distribute skill changes, but they still add a versioned artifact to maintain.

## Other clients later

Keep one repository and add client manifests when there is a concrete distribution requirement. The earlier OpenAI package remains a separate draft and should be revalidated before migration. An OpenAI app identifier is not a portable MCP configuration. No ChatGPT, Codex, or Claude submission is part of this release.
