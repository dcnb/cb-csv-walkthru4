## Step 4: Configure Your Site for Psychiana

Great! You've edited metadata. Now let's configure the site to actually **use** the Psychiana collection. This is a critical step—without it, your site won't know which CSV file to read!

### 📖 Theory: Jekyll Configuration and the _config.yml File

**Jekyll** is a static site generator that transforms your metadata and templates into a complete website. It reads `_config.yml` to understand:

- **Site settings**: Title, tagline, description
- **Collection settings**: Which metadata CSV to use
- **Deployment settings**: URL and baseurl for publishing

The most important setting for CollectionBuilder is the `metadata:` field. This tells Jekyll which CSV file in `_data/` contains your collection data.

> [!IMPORTANT]
> After changing `_config.yml`, you must restart Jekyll for changes to take effect (we'll do this in the next step when we preview the site).

### ⌨️ Activity: Point Your Site to the Psychiana CSV

Currently, your site is configured to use demo metadata. Let's change it to use the Psychiana collection.

**Part 1: Edit the Configuration**

1. In your Codespace, open `_config.yml` (you may have edited this in Step 1!)
2. Find line 37, which says: `metadata: demo-compoundobjects-metadata`
3. Change it to: `metadata: psychiana`

   **Before:**
   ```yaml
   metadata: demo-compoundobjects-metadata
   ```

   **After:**
   ```yaml
   metadata: psychiana
   ```

> [!NOTE]
> Notice we write `psychiana`, not `psychiana.csv`—Jekyll automatically looks in the `_data/` folder and adds the `.csv` extension.

4. While you're here, let's also update the site title and description. **These are suggested values—feel free to customize them however you want!**
   - Line 21: `title: Psychiana Digital Collection`
   - Line 23: `tagline: A Mail-Order Religion from Moscow, Idaho`
   - Line 26: `description: "The Psychiana Digital Collection documents Frank B. Robinson's mail-order religion (1928-1948)."`

5. **Save the file** (`Ctrl+S` or `Cmd+S`)

**Part 2: Restart Jekyll to See Your Changes**

Since you changed `_config.yml`, you need to restart Jekyll for the changes to take effect.

1. Go back to the **TERMINAL** tab at the bottom of VS Code
2. Press `Ctrl+C` to stop the Jekyll server (not `Cmd+C` on Mac!)
   - You'll see the command prompt return
3. Run the server again:
   ```bash
   bundle exec jekyll serve
   ```
4. Once it starts, click "Open in Browser" or go to the PORTS tab and click the globe icon 🌐
5. **Refresh your browser** to see the Psychiana collection!

Notice the changes:
- New title and tagline on the home page
- Different items in Browse (from psychiana.csv)
- Different map points (from Psychiana metadata)
- The item you edited in Step 2 should now appear!

> [!TIP]
> Leave Jekyll running! In the next step, you'll customize the theme and see changes reflected immediately without needing to restart.

**Part 3: Commit Using Source Control**

Now let's commit these important configuration changes.

1. Open the **Source Control** panel (left sidebar icon)
2. **Stage** `_config.yml` by clicking the **+** button
3. **Write a commit message**: `Configure site for Psychiana collection`
4. **Commit** the change
5. **Sync** to GitHub

Wait for Mona to check your work! 🤖

> [!NOTE]
> **After syncing, come back to this Issue tab and refresh the page** (`Cmd+R` on Mac or `Ctrl+R` on Windows/Linux) if you don't see the next step appear within a minute or two.

<details>
<summary>Having trouble? 🤷</summary><br/>

- The `metadata:` field is in the "COLLECTION SETTINGS" section of `_config.yml`
- Make sure you write `metadata: psychiana` exactly (no quotes, no `.csv`)
- YAML is picky about spacing—keep the same indentation as the original
- Don't forget to save before staging and committing!
- You can edit multiple lines before committing—Git will track all changes to the file

</details>
