# Getting Started with GitHub Codespaces

Start coding in the cloud with GitHub’s powerful, browser-based editor.

<!-- TODO: link to github lesson -->
## Get a GitHub Account

To use GitHub Codespaces, you’ll need a free GitHub account.

👉 Go to [https://github.com](https://github.com) and click **Sign up**.  
Choose a username, email, and password, then follow the steps to verify your account.

Already have a GitHub account? Great — you’re ready to go!

## Create a Repository for Your Project

A **repository** (or "repo") is where your code lives.

<!-- TODO: add link to codespace template -->
1. Go to your GitHub dashboard.
2. Click the green **"New"** button to create a new repository.
3. Give your repo a name (like `my-first-app`).
4. Choose public or private.
5. Check **Add a README file**. <!-- TODO: explain why README is important-->
6. Click **Create repository**.

## GitHub Codespaces

**Codespaces** are cloud-based coding environments.  
They give you a full editor (in this case VS Code) with your code and tools, running right in the browser.

### Why use Codespaces?

- No setup required
- Works on any device that can run a web browser
- All your code and environment in one place

## Start Your First Codespace

<!-- TODO: add screenshot -->
1. Go to your new repository on GitHub.  
2. Click the green **Code** button.  
3. Choose the **Codespaces** tab.  
4. Click **"Create codespace on main."**

GitHub will launch your development environment in the browser.

### Codespace (VSCode) Layout

<!-- TODO: add screenshot -->
- **Explorer (left)**: files and folders  
- **Editor (center)**: where you write code  
- **Terminal (bottom)**: run commands  
- **Tabs (top)**: open files or terminals  

<!-- TODO: add shortcuts -->

<!-- TODO: launch your app with python script -->

## Launching Your App with `bin/server`

<!-- TODO:
  have users write their own bin/server bash script
  show there is nothing fancy, just a script in the folder
-->
Some apps include a shortcut script to start a server. In the terminal, type:

```bash
bin/server
```

<!-- TODO: add screenshots to ports -->
This will start your app locally. GitHub will show you a URL (forwarded port) to view it live in the browser.

## Hello, world

Let’s try editing the app:

<!-- TODO: explain how index.html is a special file -->
Create a file like `index.html`

Add a simple message, like:

```html
<h1>Hello, world!</h1>
```

Save the file. Refresh the preview tab to see your changes!

<!-- TODO: Adding multiple files, paths -->

## Git Commit and Sync

Save your work to GitHub using Git.

### In the terminal

```bash
git add .
git commit -m "Add homepage and hello world"
git push
```

### Or in VSCode

<!-- TODO: add screenshot -->
Click the Source Control icon in the sidebar (looks like a branch).

- Type a commit message.
- Click the checkmark to commit.
- Click Sync Changes to push to GitHub.

<!-- TODO: explain how saving in codespace is not sufficient. consider them disposable. -->
Your code is now saved online!

You Did It! You’ve gotten the basics of running a GitHub Codespace.

- ✅ Created a GitHub repository
- ✅ Launched a Codespace
- ✅ Ran and edited a static web page
- ✅ Committed and synced your code

You're now coding with GitHub Codespaces — no installation needed.
