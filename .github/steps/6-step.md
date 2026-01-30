## Step 6: Customize the About Page

Your collection is looking great! Now let's add a personal touch by customizing the **About page**. This is where you tell visitors about your collection.

### 📖 Theory: Markdown and Content Pages

CollectionBuilder uses **Markdown** to create content pages. Markdown is a simple markup language that converts plain text to formatted HTML:

- `**bold**` → **bold**
- `*italic*` → *italic*
- `# Heading` → Heading (h1)
- `## Subheading` → Subheading (h2)
- `[link text](url)` → clickable link
- `- List item` → bulleted list

Markdown is easier to write than HTML but still creates beautiful formatted pages.

> [!TIP]
> Markdown files end in `.md` and live in the `pages/` directory. Jekyll converts them to HTML when building your site.

### ⌨️ Activity: Write Your About Page

Let's customize the About page with information about the Psychiana collection (or make it about your own imaginary collection!).

**Part 1: Edit the About Page**

1. In your Codespace, navigate to the `pages` folder in the file explorer
2. Click to open `about.md`

3. You'll see **front matter** (YAML) at the top between `---` marks. Leave that alone—it tells Jekyll how to process the page.

4. Below the front matter, replace the existing content with your own! Here's a template to get started:

```markdown
## About the Psychiana Digital Collection

The Psychiana Digital Collection documents one of the most fascinating religious movements of the 20th century.

### What Was Psychiana?

Psychiana was a mail-order religion founded by Frank B. Robinson in Moscow, Idaho in 1928. At its peak, it reached hundreds of thousands of subscribers worldwide through magazine advertisements and lessons sent by mail.

### The Collection

This digital collection includes:

- **Photographs** of Frank B. Robinson, his staff, and Psychiana headquarters
- **Radio programs** from the "Good News" series
- **Advertisements and promotional materials**
- **Business documents and correspondence**

The collection demonstrates Psychiana's innovative use of mass media and modern business techniques to spread its New Thought philosophy.

### Learn More

Visit the full collection at the [University of Idaho Library](https://www.lib.uidaho.edu/digital/psychiana/).
```

Feel free to modify this text, add your own sections, or write something completely different!

5. **Save the file** (`Ctrl+S` or `Cmd+S`)

**Part 2: Commit Using Source Control**

1. Open the **Source Control** panel
2. **Stage** `pages/about.md` by clicking the **+** button
3. **Commit message**: `Customize About page`
4. **Commit** and **Sync** to GitHub

> [!NOTE]
> If you still have Jekyll running from Step 5, you can refresh your browser to see the updated About page! Otherwise, you'll see it when you publish to GitHub Pages in the next step.

Wait for Mona to check your work! 🤖

<details>
<summary>Having trouble? 🤷</summary><br/>

- The About page is at `pages/about.md`, not `pages/about.html`
- Don't delete the front matter (the part between `---` marks at the top)
- Markdown is forgiving—you can't really break it. Experiment!
- If you want to preview your changes, run `bundle exec jekyll serve` in the terminal and refresh the browser
- Make sure to save the file before staging and committing

</details>
