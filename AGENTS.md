# ActivitySmith plugins

- This public repository packages ActivitySmith's hosted MCP server. Keep backend implementation and credentials out of it.
- Keep the integration MCP-only. Do not add skills, hooks, commands, local servers, or copied tool schemas unless a concrete client limitation requires them.
- Keep one shared MCP configuration at `plugins/activitysmith/mcp.json`. Client manifests reference it relative to the plugin root.
- Cursor and Grok Bot use the Cursor submission route. Grok Build uses the separate `xai-org/plugin-marketplace` catalog. Verify current requirements before submitting.
- Do not describe a package as marketplace-listed until its listing has been verified. Repository publication and marketplace acceptance are separate states.
- Preserve backward compatibility at the hosted MCP endpoint. Manifest, endpoint, or authentication changes may require plugin releases and marketplace review.
- Use natural product copy: Push Notifications, Live Activities, then Lock Screen Widgets when these appear together. Remote approvals return a user's decision; ActivitySmith does not enforce the agent's later actions.
- No em dashes in prose. Use the landing repository's `docs/product-messaging-reference.md` for capability wording when available.
