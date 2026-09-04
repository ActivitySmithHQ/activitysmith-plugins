# Marketplace submission

Reviewed September 4, 2026. Package prepared; submissions have not been sent.

## Cursor and Grok Bot

Use the [Cursor publishing page](https://cursor.com/marketplace/publish). The logged-out page requires sign-in to submit a plugin publisher application. Details behind that sign-in have not yet been verified.

The [Cursor plugin reference](https://cursor.com/docs/reference/plugins) requires a public Git repository, valid manifest, clear description, valid component paths, usage documentation, and local testing. A committed logo is recommended. This repository uses its documented multi-plugin layout with one plugin.

Submission values:

| Field | Value |
| --- | --- |
| Name | ActivitySmith |
| Identifier | `activitysmith` |
| Repository | `https://github.com/ActivitySmithHQ/activitysmith-plugins` |
| Plugin directory | `plugins/activitysmith` |
| Publisher | ActivitySmith |
| Contact | `support@activitysmith.com` |
| Website | `https://activitysmith.com` |
| Documentation | `https://activitysmith.com/docs/mcp-server` |
| Privacy | `https://activitysmith.com/legal/privacy-policy` |
| Terms | `https://activitysmith.com/legal/terms-of-service` |
| MCP endpoint | `https://mcp.activitysmith.com/mcp` |
| Authentication | OAuth with browser consent; no user-supplied API key |
| Components | One hosted MCP server; no skills or executable hooks |
| Intended clients | Cursor and Grok Bot |

Suggested description:

> Bring updates from your AI agents to your iPhone and iPad. Get notified when work finishes, follow progress on your Lock Screen, and respond when an agent needs your approval.

Reviewer note:

> This package connects to ActivitySmith over Streamable HTTP and OAuth. Users sign in to their ActivitySmith account and approve access. No local runtime or API key setup is required. Please review availability in both Cursor and Grok Bot. Remote approvals return the user's decision; the requesting agent remains responsible for the underlying action.

## Connection details for reviewers

The plugin connects to `https://mcp.activitysmith.com/mcp` over Streamable HTTP. OAuth discovery points to `https://activitysmith.com`, with authorization, token, and registration endpoints at `/oauth/authorize`, `/oauth/token`, and `/oauth/register`. Clients request `mcp:read` and `mcp:write` as needed and manage the user's OAuth credentials.

ActivitySmith receives tool arguments and performs the requested operations in the authorized account. Notification content, activity updates, and approval requests may be delivered to paired devices. The package contains no credentials, executable hooks, or local telemetry. See ActivitySmith's [privacy policy](https://activitysmith.com/legal/privacy-policy) and [terms](https://activitysmith.com/legal/terms-of-service) for service practices.

## Fresh-install check before submitting

1. Copy or symlink `plugins/activitysmith` into `~/.cursor/plugins/local/activitysmith`, following [Cursor's local testing instructions](https://cursor.com/docs/plugins). Check for an existing local package before creating that path.
2. Reload Cursor and confirm that the plugin exposes exactly one MCP server. Avoid enabling duplicate direct and plugin connections during the test.
3. Complete OAuth in the browser. Verify tools are discovered, then perform a read-only account or history request.
4. With a test account and paired device, explicitly request one Push Notification, a Live Activity start/update/end cycle, and an approval. Verify both approval and rejection handling. Use the compatibility approval tools if the client does not support MCP Tasks.
5. Reconnect and confirm the integration still works. Check authentication failures and expired access produce actionable errors.
6. Record client versions and results. After review or preview access, repeat the relevant checks in Grok Bot and verify that the listing is discoverable in both products.

Production checks already completed on September 4, 2026: unauthenticated MCP returns 401 with OAuth discovery; discovery advertises read/write scopes, PKCE S256, refresh tokens, dynamic registration, and client metadata documents. These checks do not establish fresh-client OAuth or end-to-end tool success.

## Optional separate Grok Build submission

Follow [xAI's contribution instructions](https://github.com/xai-org/plugin-marketplace/blob/main/CONTRIBUTING.md). Add a remote entry to `.grok-plugin/marketplace.json` in that catalog. Use this public repository, `source.path` of `plugins/activitysmith`, and a full reachable 40-character commit SHA.

Use brand-scoped discovery keywords such as `activitysmith` and `activitysmith notifications`, and owned domains such as `activitysmith.com`. Generic terms such as `notifications` should not trigger xAI's product-install suggestions.

Regenerate and commit the index with `python3 scripts/generate-plugin-index.py`, then run `python3 scripts/validate-catalog.py` and `python3 scripts/generate-plugin-index.py --check`. Submit the catalog change through a PR after local client testing. Later package updates require a SHA update and regenerated index. No Grok Build PR has been opened for this package.

## Release status

- Package metadata and public source: prepared.
- Cursor's official template validator: passed; its missing-hooks warning is expected for this MCP-only package.
- Shared MCP paths, JSON, logo, and absence of embedded credentials: checked.
- Production OAuth discovery: checked.
- Fresh Cursor plugin installation and OAuth: pending.
- Grok Bot installation and tool behavior: pending.
- Cursor publisher application and plugin review: pending.
- Optional Grok Build catalog review: not submitted.

Record submission URLs and acceptance here when they exist. Publishing this repository alone does not make ActivitySmith discoverable in either marketplace.
