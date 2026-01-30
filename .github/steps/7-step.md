## Step 7: Publish to GitHub Pages

You've built an amazing digital collection! Now let's publish it to the web with **GitHub Pages** so anyone can visit your collection.

### 📖 Theory: GitHub Pages and Static Site Deployment

**GitHub Pages** is a free hosting service from GitHub that publishes static websites directly from your repository. When you push commits, GitHub Actions automatically:

1. Runs Jekyll to build your site
2. Generates HTML, CSS, and JavaScript files
3. Deploys them to a public URL

Your collection will be available at: `https://[username].github.io/[repository-name]`

CollectionBuilder sites are **static**, meaning:
- No database required
- Fast loading
- Free hosting on GitHub Pages
- Easy to preserve and maintain

> [!TIP]
> GitHub Pages is free for public repositories. Your collection will be accessible to anyone on the internet!

### ⌨️ Activity: Configure and Deploy Your Site

Let's set up GitHub Pages and configure your site for production.

**Part 1: Stop Your Codespace**

Before we publish, let's stop the Codespace to save your resources.

1. If Jekyll is still running, press `Ctrl+C` in the TERMINAL to stop it
2. Look at the **bottom-left** of your VS Code window
3. Click the **Codespaces** button (it shows your Codespace name)
4. In the menu that appears, select **"Stop Current Codespace"**
   - OR: Click the command palette at top (`Cmd+Shift+P` / `Ctrl+Shift+P`), type "stop", and select "Codespaces: Stop Current Codespace"
5. Wait for the Codespace to stop

> [!TIP]
> Stopping your Codespace when you're done saves your free monthly hours! You can always restart it later.

**Part 2: Return to GitHub Web Interface**

Now let's go back to your repository on GitHub to continue.

1. Go back to your **Issue tab** in your browser (where you're reading these instructions)
2. **Right-click** the **Code** button at the top-left of the page
3. Select **"Open link in new tab"**
4. You're now viewing your repository in the regular GitHub web interface (not Codespaces)

**Part 3: Enable GitHub Pages**

1. In your repository, click **Settings** (tab at the top right)
2. In the left sidebar, click **Pages**
3. Under "Build and deployment", set **Source** to **GitHub Actions**
   - This tells GitHub to use the Jekyll workflow included with CollectionBuilder

> [!NOTE]
> CollectionBuilder includes a `.github/workflows/jekyll.yml` file that automatically builds and deploys your site when you push to the main branch.

**Part 4: Configure URLs via GitHub Web Interface**

Now we'll edit `_config.yml` one more time, but this time using GitHub's web editor (not Codespaces).

1. In your repository (on GitHub), click on the `_config.yml` file
2. Click the **pencil icon** (✏️) at the top-right to edit the file
3. Update these deployment settings with **your** GitHub username and repository name:

   - Line 11: `url: https://[username].github.io`
   - Line 13: `baseurl: /[repository-name]`
   - Line 15: `source-code: https://github.com/[username]/[repository-name]`

   **Example** (if your username is `octocat` and your repo is `my-psychiana-collection`):
   ```yaml
   url: https://octocat.github.io
   baseurl: /my-psychiana-collection
   source-code: https://github.com/octocat/my-psychiana-collection
   ```

> [!IMPORTANT]
> The `baseurl` must start with `/` and match your repository name exactly. The `url` should NOT include the repository name.

4. Click the **"Commit changes..."** button at the top-right
5. In the dialog that appears, edit your commit message if you'd like: `Configure for GitHub Pages deployment`
6. Click **"Commit changes"** to save

**Part 5: Watch the Deployment**

1. Go to the **Actions** tab in your repository on GitHub
2. You should see a workflow running (yellow dot 🟡)
3. Wait for it to complete (green checkmark ✅) — this takes 2-5 minutes
4. Once complete, visit your live site at:
   ```
   https://[username].github.io/[repository-name]
   ```

🎉 **Congratulations!** Your digital collection is now live on the web!

Share your published collection URL in the comments below! 🌐

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure the `url` and `baseurl` match your GitHub username and repository name exactly
- The `baseurl` should start with `/` (e.g., `/my-repo`, not `my-repo`)
- If the Actions workflow fails, click on it to see error details
- It can take a few minutes after the green checkmark for the site to be fully live
- If you see 404 errors, double-check your `baseurl` setting matches your repository name
- Need to find your username and repo name? Look at the URL of your repository page on GitHub

</details>
