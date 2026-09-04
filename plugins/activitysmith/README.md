# ActivitySmith

Connect your AI agent to your iPhone or iPad through ActivitySmith.

- Send Push Notifications when work finishes or needs attention.
- Show task progress with Live Activities on the Lock Screen.
- Update values shown in Lock Screen Widgets.
- Send remote approvals and receive your decision.
- Update the App Icon Badge Count and review notification or activity history.

ActivitySmith returns approval decisions to the requesting agent. The agent remains responsible for waiting for the decision and carrying out the underlying action.

## Connect your account

You need an ActivitySmith account and the ActivitySmith iOS app with a paired device. Sending events requires an active trial or subscription. See [pricing](https://activitysmith.com/pricing).

The plugin connects to `https://mcp.activitysmith.com/mcp` using Streamable HTTP and OAuth. Sign in to ActivitySmith and approve the requested access in your browser. No API key, CLI, or local server is needed.

OAuth discovery points to `https://activitysmith.com`. The authorization, token, and client registration endpoints are `/oauth/authorize`, `/oauth/token`, and `/oauth/register` on that origin. Clients request `mcp:read` and `mcp:write` as needed. The package contains no credentials. Your MCP client manages OAuth credentials.

The remote server receives tool arguments and performs the requested ActivitySmith operations in the authorized account. Notification content, activity updates, and approval requests may be delivered to paired devices. This package adds no local scripts or telemetry. ActivitySmith's service practices are described in its [privacy policy](https://activitysmith.com/legal/privacy-policy) and [terms](https://activitysmith.com/legal/terms-of-service).

## Try it

- "Send me a push notification when this task finishes."
- "Show the progress of this task with a Live Activity."
- "Ask me for approval before deploying anything to production."

Use account-wide delivery for ordinary requests. Tags organize content; Channels optionally target users or devices when routing is needed.

## Installation status

The package is prepared for marketplace review. It is not yet listed in the Cursor, Grok Bot, or Grok Build marketplaces.

For direct Cursor installation today, use the [ActivitySmith MCP setup guide](https://activitysmith.com/docs/mcp-server). Maintainers can test this directory as a local Cursor plugin using the [documented local plugin workflow](https://cursor.com/docs/plugins).

## Updates

Tool descriptions, schemas, and execution stay on the hosted MCP server. Compatible server improvements do not require updating this package. Clients may need to reconnect or start a new session to refresh cached tools. Package metadata, endpoint, authentication, and breaking changes may still require a new package version and review.
