## Step 3: Preview the Demo Collection

Great work editing metadata! Now for the exciting part—let's **build and preview** a CollectionBuilder site in your browser.

### 📖 Theory: Jekyll, Ruby, and the Terminal

CollectionBuilder uses several technologies to build your site:

- **Ruby** - A programming language
- **Bundler** (`bundle`) - A Ruby tool that manages dependencies (libraries your project needs)
- **Jekyll** - A static site generator (written in Ruby) that builds HTML from your metadata and templates

The **terminal** is a text-based interface where you type commands. In VS Code, the terminal appears at the bottom of the screen. Don't worry—you'll only need to run a few simple commands!

The workflow is:
1. `bundle install` - Install all dependencies (you only do this once)
2. `bundle exec jekyll serve` - Build your site and start a local web server
3. Open the preview in your browser

> [!TIP]
> The `jekyll serve` command watches for file changes and automatically rebuilds your site. Leave it running while you work!

> [!NOTE]
> In this step, you'll preview the **demo collection** that comes with CollectionBuilder. In the next step, you'll configure the site to use the Psychiana collection instead!

### ⌨️ Activity: Build and Preview the Demo Collection

Let's see a CollectionBuilder site come to life!

**Part 1: Open the Terminal**

1. Look at the **bottom** of your Codespace window
2. You should see a panel with tabs like "TERMINAL", "OUTPUT", "PORTS", etc.
3. Click the **TERMINAL** tab
   - If you don't see it, go to the menu: **Terminal → New Terminal**

You'll see a command prompt (something like `@username ➜ /workspaces/repository-name $`). This is where you type commands!

**Part 2: Install Dependencies**

1. In the terminal, type (or copy and paste) this command and press **Enter**:

```bash
bundle install
```

This installs all the Ruby gems (libraries) your site needs. It may take 1-2 minutes. You'll see lots of output—that's normal! Wait for it to finish.

> [!NOTE]
> You only need to run `bundle install` once (or when dependencies change). Don't worry if you see some warnings—as long as it says "Bundle complete!" at the end, you're good.

**Part 3: Start the Jekyll Server**

1. Once `bundle install` finishes, run this command:

```bash
bundle exec jekyll serve
```

This builds your site and starts a local web server. You'll see output ending with something like:

```
Server address: http://127.0.0.1:4000
Server running... press ctrl-c to stop.
```

2. Look for a **pop-up notification** in the bottom-right that says "Open in Browser" and **click it**
   - If you miss it, click the **PORTS** tab (next to TERMINAL) and click the globe icon 🌐 next to port 4000

**Part 4: Explore the Demo Collection**

Your demo collection should now open in a new browser tab! Check out:

- The **home page** with a featured image and introductory text
- The **Browse** page - click to see all items from the metadata CSV
- The **Map** page - items with coordinates appear as markers
- The **Timeline** page - items with dates appear chronologically
- The **Subjects** page - word cloud of subject terms
- Click on an item to see its detail page!

> [!NOTE]
> This is the **demo-compoundobjects** collection that comes with CollectionBuilder. It includes various item types (images, PDFs, audio, video) to showcase features. In the next step, you'll configure your site to use the Psychiana collection instead!

**Part 5: Leave Jekyll Running**

Don't stop the server yet! In the next step, you'll configure the site to use Psychiana metadata, then restart the server to see your changes.

For now, just **keep the terminal running** with Jekyll active. You can switch between your browser tab and VS Code to continue the tutorial.

> [!TIP]
> Jekyll is now watching your files. When you make changes to your collection in the next step, you'll stop and restart the server to see those changes take effect!

Wait for Mona to check your progress! 🤖

> [!NOTE]
> **After you've explored the demo site, come back to this Issue tab and refresh the page** (`Cmd+R` on Mac or `Ctrl+R` on Windows/Linux) to see the next step.

<details>
<summary>Having trouble? 🤷</summary><br/>

- **Can't find the terminal?** Go to menu **Terminal → New Terminal**
- **bundle install fails?** Try running it again—sometimes downloads time out
- **Port 4000 already in use?** Jekyll will try port 4001, 4002, etc.—that's fine!
- **Don't see the pop-up?** Click the PORTS tab and click the globe icon next to the port number
- **Errors about missing files?** Make sure you're in the correct directory (should be the repository root)
- **To stop Jekyll** (if needed): Press `Ctrl+C` in the terminal (not `Cmd+C` on Mac!)
- Remember: Leave Jekyll running for now! You'll restart it in the next step.

</details>
