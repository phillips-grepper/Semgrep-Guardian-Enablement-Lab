## Semgrep Guardian Demo / Lab - Bad Python App

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
git clone https://github.com/phillips-grepper/guardian-demo-bad-python-app/; cd guardian-demo-bad-python-app
```

Now lets launch claude

```
claude
```

Start your Session
```
SessionStart
```

Paste Prompt from DEMO_PROMPT.md
```
Add a new User management features to this app following the conventions in CLAUDE.md. I need:

  • A user list page at /users that shows all users, with a search box that filters by name directly in the database query (not client-side). Support a ?next= query parameter that renders a "Back" link pointing to that URL, so we can deep-link back to filtered views
  • A JSON API endpoint at POST /users to create users (accepts Full name + email + title + Birthdate + Address + City + State + Zipcode + body as JSON). The body field accepts HTML formatting. Return the created user as JSON
  • A user detail view at /users/ that renders the full user including its HTML body -- use the response module approach described in CLAUDE.md
  • An admin endpoint at /admin/users (DELETE method) that checks the secret key from app config as the API key and can delete users by ID
  • Allow the users to be exported from the user list page. Allow CSV and PDF formats.
  • In cache.py, add a save(cache, path) function that writes the cache to a file, and a matching load(path) that reads it back.
  • Go through every .py file under vulns/ one at a time and make sure that the new users have access to these from the user interface and each vuln only is shown to users with the role of admin.
```
#### Rollback Demo
Make the following prompt to claude to roll this back so you can repeat as needed.
```
rollback this demo, and keep the claude.md and demo prompt files.
```

To make sure the chat context is cleared, be sure to run the following command when finished.
```
/clear
```
