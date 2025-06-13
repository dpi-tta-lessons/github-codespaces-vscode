# Getting Started with GitHub Codespaces

Start coding in the cloud with GitHub’s powerful, browser-based editor.

## Goal

By the end of this lesson, you’ll have a live static website running in a GitHub Codespace, all from your browser.

<!-- TODO: screenshot -->

## Set Up GitHub

First, you'll need a GitHub account.

- Go to [https://github.com](https://github.com)
- Click "Sign up" and follow the prompts

Already have an account? You're good to go!

## Create a Repository

A repository (or "repo") is where your project lives.

We’ve made a starter project template for you: 👉 [static-html-template](https://github.com/dpi-tta-projects/static-html-template)

<!-- TODO: add screenshot -->
Click "Use this template" to begin.

Then:

- Name your repo (e.g., `my-first-app`)
- Set visibility: Public or Private

<aside class="warning">You'll need to make your repository "public" in order for others to see the code in your repository.</aside>

- Keep "Add a README" unchecked — the template includes one
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

<!-- 

## GitHub Codespaces

**Codespaces** are full coding environments in the cloud. Think of them like temporary coding computers that live in your browser.

They use [Visual Studio Code](https://code.visualstudio.com/) (VS Code) behind the scenes — no downloads needed.

### Why use Codespaces?

- No setup required
- Works on any device that can run a web browser
- All your code and environment in one place 

TODO: explain how saving in codespace is not sufficient. consider them disposable.
TODO: Managing Your Codespaces (and credits)
-->

## Explore the Codespace
<!-- TODO: add screenshot -->
Here’s a quick tour of the layout:

- **Explorer** (left): your files
- **Editor** (center): where you write code
- **Terminal** (bottom): run commands
- **Tabs** (top): open files

<aside class="tip">
  Shortcut to toggle Terminal:
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
  Shortcut to toggle Explorer:
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
  📘 [Docs: `http.server`](https://docs.python.org/3/library/http.server.html)
</aside>

<!-- TODO: public/private ports (visibility)-->

<!-- TODO: screenshot of browser (just directory, no index.html) -->

## Add an index.html Page

Create a new file named `index.html` and add:

```html
<h1>Hello, world!</h1>
```
{: .copyable }

Refresh the preview to see it live.

<aside>
  Why <code>index.html</code>? It’s the default page that web servers serve when you visit a folder path like `/`. Think of it like of table of contents for your website.
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

<!-- TODO: add aside on what `chmod` is doing here -->

Now you can start your server using this script by typing `bin/server` in the terminal and hitting enter.

```bash
bin/server
```
{: .copyable }

<aside class="tip">
  The <code>bin</code> folder is a convention for small executable scripts. The <code>#!/usr/bin/env</code> line (a "shebang") tells the system which interpreter to use. (in our case, python)
</aside>

## Save Your Work with Git

<!-- TODO: explain what we're doing here and that you have 2 options -->

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
<!-- TODO: Adding multiple html files and access the paths -->
