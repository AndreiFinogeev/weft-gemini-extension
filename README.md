# Weft for Gemini CLI

Drive your [Weft](https://letsweft.com) Scrumban board without leaving the
terminal: capture tasks as you code, move work across Backlog → Todo → Doing →
Done, and plan time-boxed sprints — just by asking Gemini.

## Install

```bash
gemini extensions install https://github.com/AndreiFinogeev/weft-gemini-extension
```

Then start `gemini` and ask:

> what's on my weft board?

On first use a browser window opens so you can sign in with your Weft account
(OAuth 2.1 — no API keys to copy). A free account takes a minute:
[letsweft.com/sign-up](https://letsweft.com/sign-up) — 50 tasks included.

## What you can ask

- "Add a high-priority task: fix the flaky CI test."
- "What am I working on right now?"
- "Move the auth refactor to Done."
- "Start a one-week sprint focused on the landing redesign."
- "Find everything about onboarding, then pull it into the current sprint."
- "File the TODOs you just added as Backlog tasks."

## What's inside

The extension connects Gemini CLI to Weft's hosted MCP server
(`https://letsweft.com/api/mcp`, Streamable HTTP) and ships a context file that
teaches Gemini the board's conventions. 18 tools cover the full surface:

| Category | Tools |
|---|---|
| Search | `search`, `fetch` |
| Board | `initialize_board`, `get_board_state`, `list_columns` |
| Tasks | `list_tasks`, `create_task`, `update_task`, `move_task`, `trash_task`, `restore_task` |
| Sprints | `list_sprints`, `get_active_sprint`, `create_sprint`, `start_sprint`, `complete_sprint`, `add_task_to_sprint`, `remove_task_from_sprint` |

Full tool reference: [letsweft.com/docs/mcp-tools](https://letsweft.com/docs/mcp-tools)

## Notes

- Deleting is safe: `trash_task` keeps tasks recoverable for 30 days.
- Your board is private; tools are scoped to your account via OAuth.
- The same MCP endpoint also works in Claude, ChatGPT, Cursor, and any
  MCP-compatible client — see [letsweft.com/integrations](https://letsweft.com/integrations).

## Support

- Docs: [letsweft.com/docs](https://letsweft.com/docs)
- Email: support@letsweft.com
- Privacy: [letsweft.com/privacy](https://letsweft.com/privacy)
