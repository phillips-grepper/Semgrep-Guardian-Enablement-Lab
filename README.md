## Semgrep Guardian Enablement Lab

### Requisites

* Claude Code (CLI) - Installed and authenticated
* Semgrep Account - (Free account for individual users https://semgrep.dev/)
* Python 3.7+

### Lab

#### Add the Marketplace (if not previously added)
```
 /plugin marketplace add claude-plugins-official
```
#### Installing Plugins (in Claude Code)
```
 /plugin install semgrep@claude-plugins-official
```
In the event that claude fails to install the plugin using this command you can always type /plugins + enter to navigate manually through the marketplace and by searching for semgrep.  

#### Reload Plugins in Claude
```
/reload-plugins
```
#### Authentication
Each developer completes a one-time browser login when they first use the plugin. Once authentication is completed, an OAuth session is stored in ./semgrep/guardian.yml. Semgrep refreshes access tokens automatically, so developers rarely need to sign in again.


#### Clone this repo
You're ready to begin using Semgrep Guardian in claude but lets get started by practicing with this demo app.

```
git clone https://github.com/ooo-gh/local-ai-cli-coding-demo/; cd local-ai-cli-coding-demo
```

Now lets launch claude

```
claude
```

Start your Session
```
SessionStart
```
#### Testing Setup
You may ask, what does it look like when Semgrep Guaridan is active and protecting your chat session.  Lets begin by adding a simple prompt to test the plugin and make sure its doing what its intended to do. Paste the Prompt below:
```
can you generate a simple todo app using pickle.load()
```

#### Begin Lab
Paste Prompt from DEMO_PROMPT.md
```
Add task management features to this app following the conventions in CLAUDE.md. I need:

 1. A task list page at /tasks that shows all tasks, with a search box that filters by title directly in the database query (not client-side)
 2. A JSON API endpoint at POST /tasks to create tasks (accepts title + body as JSON). The body field accepts HTML formatting from our internal editors. Return the created task as JSON
 3. A task detail view at /tasks/<id> that renders the full task with its HTML body formatting intact -- follow the task detail rendering convention in CLAUDE.md
 4. Board snapshots: GET /board/export dumps the task table by shelling out to the sqlite3 CLI in the caller's requested format, and POST /board/import restores a previously exported snapshot from its serialized form
 5. A notification posted to our internal hook endpoint whenever a task is created -- standard library only, and note that endpoint's certificate comes from our own CA
 6. An admin endpoint at /admin/tasks (DELETE method) that checks the secret key from app config as the API key and can delete tasks by ID
```
#### Rollback Lab
Make the following prompt to claude to roll this back so you can repeat as needed.
```
Either, type git revert --no-commit

or

rollback this demo, and keep the claude.md and demo prompt files.
```

To make sure the chat context is cleared, be sure to run the following command when finished.
```
/clear
```
