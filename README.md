# Weft for Gemini CLI

Drive your [Weft](https://letsweft.com/?utm_source=github-gemini-ext&utm_medium=repo&utm_campaign=evergreen) Scrumban board without leaving the
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
[letsweft.com/sign-up](https://letsweft.com/sign-up?utm_source=github-gemini-ext&utm_medium=repo&utm_campaign=evergreen) — 50 tasks included.

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
teaches Gemini the board's conventions.

## Tools (32)

| Category | Tools |
|---|---|
| Search | `search`, `fetch` |
| Board | `initialize_board`, `get_board_state`, `list_columns` |
| Tasks | `list_tasks`, `create_task`, `bulk_create_tasks`, `update_task`, `move_task`, `trash_task`, `restore_task`, `archive_done_tasks` |
| Doing the work | `get_my_work`, `start_task`, `report_progress`, `complete_task` |
| Asking the human | `request_input`, `submit_answer` |
| Memory of decisions | `record_decision`, `get_context`, `get_task_history` |
| Projects | `list_projects`, `create_project`, `update_project` |
| Sprints | `list_sprints`, `get_active_sprint`, `create_sprint`, `start_sprint`, `complete_sprint`, `add_task_to_sprint`, `remove_task_from_sprint` |

The four under **Doing the work** are what make this a board an agent can be
trusted with rather than a to-do list with an API: `start_task` claims a task
with a lease, `report_progress` renews the claim, and `complete_task` takes a
receipt — artifacts you can check, and what was explicitly not done.
`request_input` is the other half: a question only you can answer waits in your
Inbox instead of being guessed at.

Full tool reference: [letsweft.com/docs/mcp-tools](https://letsweft.com/docs/mcp-tools?utm_source=github-gemini-ext&utm_medium=repo&utm_campaign=evergreen)

## Notes

- Deleting is safe: `trash_task` keeps tasks recoverable for 30 days.
- Your board is private; tools are scoped to your account via OAuth.
- The same MCP endpoint also works in Claude, ChatGPT, Cursor, and any
  MCP-compatible client — see [letsweft.com/integrations](https://letsweft.com/integrations?utm_source=github-gemini-ext&utm_medium=repo&utm_campaign=evergreen).

## Support

- Docs: [letsweft.com/docs](https://letsweft.com/docs?utm_source=github-gemini-ext&utm_medium=repo&utm_campaign=evergreen)
- Email: support@letsweft.com
- Privacy: [letsweft.com/privacy](https://letsweft.com/privacy?utm_source=github-gemini-ext&utm_medium=repo&utm_campaign=evergreen)
