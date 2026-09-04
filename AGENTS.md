# ActivitySmith plugins

- This public repository packages ActivitySmith's hosted MCP server. Keep backend implementation and credentials out of it.
- READMEs and the GitHub description are for users discovering ActivitySmith. Lead with what it does, device/account setup, installation, and example requests. Mention MCP briefly as the connection method. Keep packaging choices, absent components, repository layout, and submission/review plans in maintainer docs; mention marketplace availability only where it affects installation.
- Keep the integration MCP-only. Do not add skills, hooks, commands, local servers, or copied tool schemas unless a concrete client limitation requires them.
- Keep one shared MCP configuration at `plugins/activitysmith/mcp.json`. Client manifests reference it relative to the plugin root.
- Write marketplace descriptions for people who do not know ActivitySmith. Cursor's per-plugin `plugin.json` overrides matching marketplace entry fields; keep their descriptions aligned. `metadata.description` describes the collection.
- Cursor and Grok Bot use the Cursor submission route. Grok Build uses the separate `xai-org/plugin-marketplace` catalog. Verify current requirements before submitting.
- Do not describe a package as marketplace-listed until its listing has been verified. Repository publication and marketplace acceptance are separate states.
- Preserve backward compatibility at the hosted MCP endpoint. Manifest, endpoint, or authentication changes may require plugin releases and marketplace review.
- Use natural product copy: Push Notifications, Live Activities, then Lock Screen Widgets when these appear together. Remote approvals return a user's decision; ActivitySmith does not enforce the agent's later actions.
- No em dashes in prose. Use the landing repository's `docs/product-messaging-reference.md` for capability wording when available.
