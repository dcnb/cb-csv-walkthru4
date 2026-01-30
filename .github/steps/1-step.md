## Step 1: Launch Codespaces and Make Your First Commit

Welcome to CollectionBuilder! In this first step, you'll set up your development environment and learn how to save changes using Git—the version control system that tracks all your edits.

### 📖 Theory: What is GitHub Codespaces?

**GitHub Codespaces** is a cloud-based development environment that runs Visual Studio Code in your browser. When you launch a Codespace, GitHub creates a virtual machine with everything you need:

- **File Explorer** (left sidebar) - Browse and open files
- **Editor** (center) - Edit code and text files
- **Source Control** (left sidebar icon) - Save and track changes with Git
- **Terminal** (bottom panel) - Run commands when needed

Codespaces are perfect for tutorials because they provide a consistent environment—everyone gets the same setup, regardless of their operating system.

> [!TIP]
> Codespaces are free for personal GitHub accounts with 120 core-hours per month and 15 GB storage.

### 📖 Theory: Understanding Git and Version Control

**Git** is a version control system that tracks changes to your files. Think of it like a detailed save history for your project. Every time you make changes, you create a "commit" (a snapshot) that you can return to later.

The Git workflow has three main steps:
1. **Edit** - Make changes to files in the editor
2. **Stage** - Select which changes to save (like putting items in a box)
3. **Commit** - Save a snapshot with a descriptive message (like sealing and labeling the box)
4. **Sync** - Upload your commits to GitHub (like shipping the box)

In VS Code, you do all of this through the **Source Control** panel—no command line required!

> [!IMPORTANT]
> Always write clear commit messages! They help you (and others) understand what changed and why.

### ⌨️ Activity: Open Codespace and Sign Your Work

Let's launch your environment and personalize the site by adding your GitHub username!

**Part 1: Navigate to Your Repository's Main Page**

First, you need to navigate to the main page of your repository (the URL will look like \`https://github.com/YOUR-USERNAME/REPO-NAME\`).

1. **Right-click** on the **Code** button (the green button you'll see at the top of your repository)
2. Select **Open link in new tab** — this keeps your Issue tab open so you can refer back to these instructions!
3. You should now have two tabs: one with this Issue (your instructions) and one with your repository's main page

> [!TIP]
> Keep both tabs open throughout the tutorial. You'll switch between reading instructions here and working in Codespaces.

**Part 2: Launch Codespace**

1. In your new repository tab, click the **Code** button (green button)
2. Click the **Codespaces** tab
3. Click **Create codespace on main**
4. Wait for the Codespace to load (this may take 1-2 minutes)

Once your Codespace opens, you'll see VS Code running in your browser!

<details>
<summary>Having trouble? 🤷</summary><br/>

Open Codespaces directly by clicking the button below:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{REPOSITORY_NAME}}?quickstart=1)

</details>

> [!NOTE]
> **While you wait for your Codespace to load**, explore some examples of CollectionBuilder sites at <a href="https://collectionbuilder.github.io/cb-examples/" target="_blank">CollectionBuilder Examples</a> (opens in new tab)! See what's possible with this framework.

**Part 3: Enable Word Wrap**

Let's make long lines easier to read by enabling word wrap!

1. Go to the menu and click **View → Word Wrap**
   - Or use the keyboard shortcut: \`Alt+Z\` (Windows/Linux) or \`Option+Z\` (Mac)
2. You'll see long lines now wrap to fit your screen width instead of scrolling horizontally

> [!TIP]
> Word wrap makes it much easier to read long lines in configuration files, CSV metadata, and Markdown documents. You can toggle it on/off anytime with \`Alt+Z\` or \`Option+Z\`.

**Part 4: Edit the Configuration File**

1. In the **file explorer** (left sidebar), click to open \`_config.yml\`
2. Find line 30 that says \`author: CollectionBuilder\`
3. Change it to \`author: YourGitHubUsername\` (replace with your actual GitHub username!)
4. **Save the file** by pressing \`Ctrl+S\` (Windows/Linux) or \`Cmd+S\` (Mac)
   - Or click **File → Save** in the menu
   - The file tab will show a white dot (●) if unsaved

> [!NOTE]
> The \`_config.yml\` file contains site-wide settings for your CollectionBuilder site. Jekyll (the static site generator) reads this file to configure your collection.

**Part 5: Commit Your Changes Using Source Control**

Now let's save your changes using Git through VS Code's visual interface!

1. Look at the **left sidebar** and click the **Source Control** icon (it looks like a branch/fork with three circles, usually the third icon from the top)
   - You should see a badge with the number "1" showing you have 1 changed file

2. In the Source Control panel, you'll see \`_config.yml\` listed under "Changes"

3. **Stage your change**: Hover over \`_config.yml\` and click the **+** (plus) button that appears
   - This moves the file to "Staged Changes"
   - Staging tells Git "I want to save this change"

4. **Write a commit message**: At the top of the Source Control panel, you'll see a text box that says "Message"
   - Click in the box and type: \`Add my GitHub username as author\`
   - Good commit messages are short and descriptive!

5. **Commit your change**: Click the **Commit** button (it's blue and appears below the message box)
   - This saves your snapshot locally in Codespaces

6. **Sync to GitHub**: Click the **Sync Changes** button that appears
   - This uploads your commit to GitHub
   - You may see a button that says "Sync Changes 1↑" (1 upload)
   - Click it to push your changes!

> [!TIP]
> If a pop-up asks "Would you like to stage all your changes?", click **Yes**. If it asks about periodically running git fetch, click **Yes** or **Ask Me Later**.

**Part 6: View Your Changes on GitHub**

Before we move on, let's see how GitHub tracks your changes!

1. Go back to your repository tab in the browser (or open your repository in a new tab)
2. Click on the \`_config.yml\` file to view it
3. Notice how your new author name appears in the file
4. Click the **History** button (or the commit count) to see your commit history
5. Click on your commit to see the **diff** — GitHub highlights deletions in red and additions in green!

This is how version control helps you track every change you make.

Wait for Mona to check your work! 🤖

> [!NOTE]
> **After syncing, come back to this Issue tab and refresh the page** (\`Cmd+R\` on Mac or \`Ctrl+R\` on Windows/Linux) if you don't see the next step appear within a minute or two.

<details>
<summary>Having trouble? 🤷</summary><br/>

- **Can't find Source Control?** Look for the icon with three connected circles in the left sidebar (usually third from top)
- **Don't see a + button?** Make sure you're hovering over the filename in the Changes section
- **File won't save?** Press \`Ctrl+S\` (or \`Cmd+S\`) and check that the white dot disappears from the file tab
- **Sync button not appearing?** You might need to click "Publish Branch" instead—that's fine, it does the same thing!
- **Commit button is grayed out?** Make sure you wrote a commit message in the text box
- The Source Control panel should show "0" changes after you successfully sync

</details>
