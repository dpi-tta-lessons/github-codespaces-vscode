# Getting Started with GitHub Codespaces

Start coding in the cloud with GitHub’s powerful, browser-based editor.

## Goal

By the end of this lesson, you’ll have a live static website running in a GitHub Codespace, all from your browser.

<!-- TODO: screenshot -->

## Set Up GitHub

First, you'll need a GitHub account.

- Go to <a href="https://github.com" target="_blank">https://github.com</a>
- Click "Sign up" and follow the prompts

Already have an account? You're good to go!

## Create a Repository

<video src="assets/create-repo-from-template.mp4" width="480" autoplay loop muted playsinline></video>

A repository (or "repo") is where your project lives.

We’ve made a starter project template for you: 👉 <a href="https://github.com/dpi-tta-projects/static-html-template" target="_blank">static-html-template</a>

Click "Use this template" to begin.

![use this template button](assets/use-this-template.png)

Then:

- Name your repo (e.g., `my-first-app`)
- Set visibility: Public or Private

<aside class="warning">You'll need to make your repository "public" in order for others to access your repository.</aside>

- Click Create repository

<aside class="tip">
  <strong>Naming convention:</strong> Use lowercase letters and dashes (e.g., <code>my-first-app</code>). This style is called <strong>kebab-case</strong> and is commonly used in web development.
</aside>

## Launch a Codespace
<!-- TODO: screenshot -->
Go to your new repo and:

- Click the green "Code" button
- Select the "Codespaces" tab
- Click "Create codespace on main"

Your browser will open a full development environment, no installs required!

<aside class="warning">
  Be patient. The first time you load a codespace may take a few minutes. Subsequent loads will be much faster.
</aside>

## Explore the Codespace
<!-- TODO: add screenshot -->
Here’s a quick tour of the layout:

- **Explorer** (left panel): your files
- **Editor** (center panel): where you write code
- **Terminal** (bottom panel): run commands
- **Tabs** (top): open files

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

## Start a Local Server

In the terminal, type:

```bash
python -m http.server 3000
```
{: .copyable }

<aside class="tip">
  This command starts a lightweight web server on port 3000 — ideal for serving static files like HTML and CSS.
</aside>

<!-- TODO: screenshot to ports tab -->
GitHub will show a URL (a "forwarded port") to preview your site.

<aside>
  <a href="https://docs.python.org/3/library/http.server.html" target="_blank">📘 Docs: http.server</a>
</aside>

<aside class="tip">
  If you'd like to access your app from any device, set the forwarded port to <strong>public</strong> in the Ports tab. This way you can access your app from your phone and share the link with friends.
</aside>

<!-- TODO: screenshot of browser (just directory, no index.html) -->

## Add an index.html Page

Create a new file named `index.html` and add:

```html
<h1>Hello, world!</h1>
```
{: .copyable }

Refresh the preview to see it live.

<aside>
  Why <code>index.html</code>? It’s the default page that web servers serve when you visit a folder path like `/`. Think of it like a "table of contents" for your website.
</aside>

## Create a `bin/server` Script

Let’s automate our server start-up.

<!-- TODO add screenshot -->
Make a folder called `bin`. Inside `bin`, create a file called `server`.

Paste this code:

```bash
#!/usr/bin/env python

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
  The <code>bin</code> folder is a convention for small executable scripts. The <code>#!/usr/bin/env</code> line (a "shebang") tells the system which interpreter to use. (in our case, python)
</aside>

## Save Your Work with Git

<aside class="warning">
  Codespaces are temporary environments. Saving your code is not enough, you must commit and push to GitHub to avoid losing your work.
</aside>

There are two ways to save your work to GitHub:

1. Use Git commands in the terminal (if you're comfortable with the command line)
2. Use the VS Code Source Control Tab (beginner-friendly)

Both methods achieve the same result.

### In the terminal

<!-- TODO: screenshot -->

```bash
git add .
git commit -m "Add homepage and hello world"
git push
```
{: .copyable }

### In the VS Code Source Control Tab

<!-- TODO: screenshot -->
Click the Source Control icon (looks like a branch)

- Write a commit message
- Click ✓ to commit
- Click Sync Changes

<aside>
  Committing your code saves a snapshot. Pushing it sends that snapshot to GitHub where it can be safely stored long term.
</aside>

Your code is now saved online!

## Manage Codespaces (and Credits)

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

Try modifying your homepage:

- Add an `<h2>` subtitle
- Include a `<p>` paragraph with a message
- Use the terminal to commit and push your changes

<aside class="tip">
  Want to go further? Try creating additional HTML files (like <code>about.html</code>) and open them at <code>/about.html</code> in your browser.
</aside>
