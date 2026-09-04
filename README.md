# ActivitySmith plugins

[ActivitySmith](https://activitysmith.com) brings updates from your AI agents to your iPhone and iPad. Get notified when work finishes, follow progress on your Lock Screen, and respond when an agent needs your approval.

Your agent can:

- Send Push Notifications when a task finishes, fails, or needs attention.
- Show ongoing work with Live Activities on your Lock Screen and Dynamic Island.
- Update business metrics and other values in Lock Screen Widgets.
- Send remote approval requests and receive your decision.
- Update the app icon badge count and review notification or activity history.

The plugin connects your agent to ActivitySmith through [MCP](https://activitysmith.com/docs/mcp-server).

## Get started

Install [ActivitySmith for iPhone and iPad](https://apps.apple.com/us/app/activitysmith/id6752254835), create an account or sign in, and follow the setup steps to pair your device. Use the same ActivitySmith account when connecting your agent.

## Connect your agent

### Cursor

1. Click [Add to Cursor](https://cursor.com/install-mcp?name=activitysmith&config=eyJ1cmwiOiJodHRwczovL21jcC5hY3Rpdml0eXNtaXRoLmNvbS9tY3AifQ%3D%3D).
2. Confirm the installation in Cursor.
3. When prompted, sign in to ActivitySmith in your browser and approve the connection.

Start a new chat and ask Cursor to send you a push notification.

For manual setup, add this entry to your `~/.cursor/mcp.json` file alongside any existing servers:

```json
{
  "mcpServers": {
    "activitysmith": {
      "url": "https://mcp.activitysmith.com/mcp"
    }
  }
}
```

### Cursor Marketplace and Grok Bot

ActivitySmith is not yet listed in the [Cursor Marketplace](https://cursor.com/marketplace) or Grok Bot's plugin directory. You can connect Cursor now using the installation link above.

### Other MCP clients

Add ActivitySmith as a remote MCP server using this URL:

```text
https://mcp.activitysmith.com/mcp
```

Complete the ActivitySmith sign-in flow in your browser. See the [MCP setup guide](https://activitysmith.com/docs/mcp-server) for client-specific instructions.

## Try it

Ask your agent for the update you want:

> Send me a push notification when this task finishes.

> Show the progress of this task with a Live Activity on my Lock Screen.

> Notify me on my iPhone if this task gets blocked.

> Ask me for approval before deploying anything to production.

For remote approvals, ActivitySmith delivers the request to your device and returns your decision to the agent. The agent then handles the action you approved.

## Learn more

- [ActivitySmith](https://activitysmith.com)
- [MCP setup and available tools](https://activitysmith.com/docs/mcp-server)
- [Pricing](https://activitysmith.com/pricing)
- [Support](mailto:support@activitysmith.com)
- [Privacy policy](https://activitysmith.com/legal/privacy-policy) and [terms of service](https://activitysmith.com/legal/terms-of-service)

## License

[MIT](LICENSE)
