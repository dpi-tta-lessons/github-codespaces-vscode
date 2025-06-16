# Getting Started with GitHub Codespaces

Start coding in the cloud with GitHub’s powerful, browser-based editor.

## Goal

By the end of this lesson, you’ll have a live static website running in a GitHub Codespace, all from your browser.

<video src="assets/goal-completed.mp4" autoplay loop muted playsinline></video>

## Set Up GitHub

First, you'll need a GitHub account.

- Go to <a href="https://github.com" target="_blank">https://github.com</a>
- Click "Sign up" and follow the prompts

Already have an account? You're good to go!

## 1. Create a Repository

<video src="assets/create-repo-from-template.mp4" autoplay loop muted playsinline></video>

A repository (or "repo") is where your project lives.

We’ve made a starter project template for you: 👉 <a href="https://github.com/dpi-tta-projects/static-html-template" target="_blank">static-html-template</a>

Click "Use this template" to begin.

![use this template button](assets/use-this-template.png)

Then:

- Name your repo (e.g., `my-first-app`)
- Set visibility: **Public** or **Private**

<aside class="warning">You'll need to make your repository "public" in order for others to access your repository.</aside>

- Click Create repository

<aside class="tip">
  <strong>Naming convention:</strong> Use lowercase letters and dashes (e.g., <code>my-first-app</code>). This style is called <strong>kebab-case</strong> and is commonly used in web development.
</aside>

## 2. Launch a Codespace

![create codespace on main](assets/create-codespace-on-main.png)

Go to your new repo and:

- Click the green "Code" button
- Select the "Codespaces" tab
- Click "Create codespace on main"

Your browser will open a full development environment, no installs required!

<aside class="warning">
  Be patient. The first time you load a codespace may take a few minutes. Subsequent loads will be much faster.
</aside>

## 3. Explore the Codespace

![codespace layout](assets/vscode.png)

Here’s a quick tour of the layout:

- **Explorer** (left panel): your files
- **Editor** (center panel): where you write code
- **Terminal** (bottom panel): run commands
- **Tabs** (top): open files

<!-- TODO: add gif showing toggling -->
<aside class="tip">
  Shortcut to toggle <strong>Terminal</strong>:
  <ul>
    <li>
      <code>Ctrl + J</code> (Windows/Linux)
    </li>
    <li>
      <code>⌘ + J</code> (Mac)
    </li>
  </ul>
</aside>

<!-- TODO: add gif showing toggling -->
<aside class="tip">
  Shortcut to toggle <strong>Explorer</strong>:
  <ul>
    <li>
      <code>Ctrl + B</code> (Windows/Linux)
    </li>
    <li>
      <code>⌘ + B</code> (Mac)
    </li>
  </ul>
</aside>

## 4. Start a Local Server

<video src="assets/starting-http-server-and-port.mp4" autoplay loop muted playsinline></video>

In the terminal, type:

```bash
python -m http.server 3000
```
{: .copyable }

<aside class="tip">
  This command starts a lightweight web server on port 3000 — ideal for serving static files like HTML and CSS.
</aside>

<aside>
  <a href="https://docs.python.org/3/library/http.server.html" target="_blank">📘 Docs: http.server</a>
</aside>

GitHub will show a URL (a "forwarded port") to preview your site. Click the ports tab in the bottom panel. Click on the 🌐 icon to open your app in a browser.

![ports tab](assets/ports.png)

<aside class="tip">
  If you'd like to access your app from any device, set the port visibility to <strong>public</strong>. This way you can access your app from your phone and share the link with friends.
</aside>

<aside class="tip">

<img src="assets/directory-listing.png" alt="server directory listing">

When you visit your Codespace preview and see <code>Directory listing for /</code>, it means your web server is running, but there’s no <code>index.html</code> file present.

Web servers look for a default file to show — usually <code>index.html</code>. If it’s missing, the server shows a list of files and folders in your project instead. This is called a "directory listing".

Once you add <code>index.html</code>, that file will be shown automatically instead of the listing.

</aside>

<aside class="tip">
  Stop your server by entering <code>Ctrl + C</code> in the terminal. This works with most terminal processes. If all else fails, you can also close the terminal running the process.
</aside>

<aside class="tip">
  <img src="assets/create-kill-terminal.png" alt="Create or Kill Terminal Instance">

  In the terminal tab, click `+` to create additional terminal instances. You can also click the trash icon to destroy the terminal instance.
</aside>

## 5. Add an index.html Page

<video src="assets/create-index-html.mp4" autoplay loop muted playsinline></video>

Create a new file named `index.html` and add:

```html
<h1>Hello, world!</h1>
```
{: .copyable }

Refresh the preview to see it live.

<aside>
  Why <code>index.html</code>? It’s the default page that web servers serve when you visit a folder path like `/`. Think of it like a "table of contents" for your website.
</aside>

<aside class="tip">
  Use the vs code explorer 'new file' and 'new folder' buttons.

  <img src="assets/explorer-new-file-folder.png" alt="vscode explorer new file / folder">
</aside>

## 6. Create a `bin/server` Script

<video src="assets/create-bin-server.mp4" autoplay loop muted playsinline></video>

Let’s automate our server start-up.

Make a folder called `bin`. Inside `bin`, create a file called `server`.

Paste this code:

```bash
#!/usr/bin/env bash

python -m http.server 3000
```
{: .copyable }

In terminal, run:

```bash
chmod +x bin/server
```
{: .copyable }

<aside class="tip">
  The <code>chmod +x</code> command makes your script executable, meaning you can run it like a regular program.
</aside>

Now you can start your server using this script by typing `bin/server` in the terminal and hitting enter.

```bash
bin/server
```
{: .copyable }

<aside class="tip">
  The <code>bin</code> folder is a convention for small executable scripts. The <code>#!/usr/bin/env</code> line (a "shebang") tells the system which interpreter to use for the script. (in our case, <code>bash</code>, the same shell we use in the terminal)
</aside>

<!-- TODO: refine this section (version control) -->

## 7. Save Your Work with Git

<aside class="warning">
  Codespaces are temporary environments. Saving your code is not enough, you must commit and push to GitHub to avoid losing your work.
</aside>

You'll notice your new files will appear in <span class="text-success">green</span> color.

![explorer diff green](assets/explorer-diff.png)

The source control tab in the left pane will also indicate that you have '2 pending changes'.

![source control indicator](assets/source-control-indicator.png)

There are two ways to save your work to GitHub:

1. Use Git commands in the terminal (if you're comfortable with the command line)
2. Use the VS Code Source Control Tab (beginner-friendly)

Both methods achieve the same result.

### In the terminal

<!-- TODO: screenshot -->
<!-- TODO: show how to see the diff -->
<!-- TODO: note on staging each file (vs all) -->
```bash
git add .
git commit -m "Add index.html with hello world and bin/server script"
git push
```
{: .copyable }

### In the VS Code Source Control Tab

<video src="assets/source-control-tab-commit-push-sync.mp4" autoplay loop muted playsinline></video>

Click the Source Control icon (looks like a branch).

![source control icon](assets/source-control-icon.png)

- Write a commit message "Add index.html with hello world and bin/server script"
- Stage the files you want to commit (click the '+' next to each file)
- Click '✓ Commit' to commit
- Click 'Sync Changes' to push to GitHub

<aside>
  Committing your code saves a snapshot. Pushing it sends that snapshot to GitHub where it can be safely stored long term.
</aside>

Your code is now saved online!

<!-- TODO: add general tip on writing commit messages -->
<!-- TODO: add warning on COMMIT_EDITMSG when you forget to write a commit message -->

<!-- TODO: move to aside? -->
## Manage Codespaces (and Credits)

<!-- TODO: add screenshot -->
Each GitHub user gets limited free hours for Codespaces. To manage or delete your environments:

- Go to [https://github.com/codespaces](https://github.com/codespaces)
- Click the "..." next to a Codespace to stop or delete it

<aside class="tip">
  Deleting unused Codespaces frees up your quota and prevents unnecessary charges.
</aside>

## Recap

You just:

- ✅ Created a GitHub repo from a template
- ✅ Launched a Codespace
- ✅ Ran a live web server
- ✅ Wrote an HTML page
- ✅ Pushed your code to GitHub

You now have a live web development environment in the cloud!

## Practice Challenge

- Add an `<h2>` subtitle
- Include a `<p>` paragraph with a message
- Use the terminal to commit and push your changes
- Create additional HTML files (like `about.html`) and open them at `/about.html` in your browser.
- Bonus: Link to your new pages using `<a>` links
