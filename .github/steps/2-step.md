## Step 2: Explore and Edit Collection Metadata

Excellent! You've made your first commit using VS Code's Source Control panel. Now let's explore the heart of CollectionBuilder: the **metadata CSV file** that describes your digital collection.

### 📖 Theory: Metadata and CSV Files

**Metadata** means "data about data"—it's information that describes your collection items. For a digital collection, metadata includes:

- **Descriptive info**: Title, description, creator, date
- **Technical info**: File location, file type
- **Administrative info**: Rights, subjects, keywords
- **Geospatial info**: Latitude, longitude (for maps!)

CollectionBuilder uses metadata to automatically generate your entire collection website. Every item, map point, timeline entry, and search result comes from your CSV file!

**CSV (Comma-Separated Values)** is a simple format for tabular data:
- Each row represents one collection item
- Each column represents one metadata field
- The first row contains column headers

CollectionBuilder reads your CSV and transforms it into:
- 📖 Item pages with details
- 🗺️ Interactive maps (using latitude/longitude)
- 📅 Timelines (using dates)
- 🔍 Search functionality
- 📊 Data visualizations

> [!TIP]
> **Real-world workflow:** Many people create and edit their metadata in **Google Sheets**, then download it as a CSV. Google Sheets is free, collaborative, and works great for metadata projects!

> [!NOTE]
> CollectionBuilder requires specific metadata fields to work properly. The two **required** fields are `objectid` and `title`. Learn more in the [CollectionBuilder Metadata Documentation](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/).

### 📖 Theory: Display Control Fields

While `objectid` and `title` are the only required fields, there are several key fields that control **how** your items display in CollectionBuilder-CSV:

- **`display_template`** - Determines the item page type (image, pdf, video, audio, etc.). This tells CollectionBuilder what kind of object you have.
- **`object_location`** - Full URL or path to the digital object file. This is what users access or download.
- **`image_small`** - Smaller image representation (~800px wide) used on item pages and visualizations
- **`image_thumb`** - Thumbnail image (~450px wide) used on Browse, Map, and Home pages

These fields work together to create a complete representation of each item. For example, a video item might have:
- `display_template: video` (tells CB it's a video)
- `object_location: https://youtu.be/abc123` (the actual video URL)
- `image_small: https://img.youtube.com/vi/abc123/hqdefault.jpg` (preview image)
- `image_thumb: https://img.youtube.com/vi/abc123/mqdefault.jpg` (thumbnail)

> [!TIP]
> Learn more about display templates and how these fields work in the [CollectionBuilder CSV Metadata documentation](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/#display-template).

### ⌨️ Activity: Explore and Edit the Psychiana Metadata

Let's examine the metadata structure for the Psychiana collection and make an edit!

**Part 1: Open the CSV File**

1. In the Codespace **file explorer** (left sidebar), navigate to the `_data` folder
2. Click to open `psychiana.csv`

You'll see many columns! Some key ones to notice:
- `objectid` - **Required** - Unique identifier (no spaces or special characters)
- `title` - **Required** - Item title
- `display_template` - Controls how the item displays (image, video, pdf, audio, etc.)
- `object_location` - URL or path to the digital object
- `image_small` and `image_thumb` - Image representations for the item
- `description` - *Optional* - Item description
- `subject` - *Optional* - Subjects/keywords (separated by semicolons)
- `latitude` and `longitude` - *Optional* - Geographic coordinates for maps
- `date` - *Optional* - Creation date (displays on timeline)

**Part 2: Explore psychiana001**

Let's look closely at the first item in the collection!

1. Find the row for `psychiana001` (should be the first data row after the header)
2. **Scroll horizontally** through the entire row by clicking and dragging in the CSV
3. As you hover over cells, notice how the column name pops up at the top! This helps you orient yourself.

This item is special—it's a **YouTube video from Northwest Public Broadcasting** about Psychiana, the mail-order religion this collection documents.

Notice these fields:
- **`display_template`** = `video` — tells CollectionBuilder this is a video item
- **`object_location`** = `https://youtu.be/x6eu5wj8b04` — the YouTube link
- **`image_small`** = `https://img.youtube.com/vi/x6eu5wj8b04/hqdefault.jpg` — YouTube-generated preview image
- **`image_thumb`** = `https://img.youtube.com/vi/x6eu5wj8b04/mqdefault.jpg` — YouTube-generated thumbnail

**Part 3: Edit the Title**

Now let's edit the title! Currently it reads:

```
"Psychiana, A Mail Order Religion Created in the Small Town of Moscow, Idaho"
```

Notice the **quotation marks** around the title? This is how CSV format handles commas in data. Since the title contains commas, it must be wrapped in quotes to prevent the CSV from treating each comma as a new column.

> [!NOTE]
> **CSV Learning Moment:** When your data contains commas, wrap it in quotes. This is why editing CSVs in Google Sheets is often easier—it handles the quoting automatically!

Your task:
1. Imagine you're the producer and want to change the title to something more enticing
2. Edit the title to your new version (be creative!)
3. **If your new title includes commas, put it in quotes** (like the original)
4. **If your title has NO commas, you can remove the quotes** (but leaving them is fine too)
5. **Save the file** (`Ctrl+S` or `Cmd+S`)

Some title ideas:
- `Mystery Religion from Small-Town Idaho`
- `The Mail-Order Faith That Reached the World`
- `Idaho's Unlikely Religious Movement`

**Part 4: Commit Your Changes**

Now let's commit your metadata edit using Source Control!

1. Click the **Source Control** icon in the left sidebar
2. You should see `_data/psychiana.csv` listed under "Changes"
3. **Stage the file**: Hover over the file and click the **+** button
4. **Write your commit message**: `Update psychiana001 title`
5. **Commit**: Click the **Commit** button
6. **Sync**: Click **Sync Changes** to push to GitHub

**Part 5: View the Diff**

Before we move on, let's see your change visualized on GitHub!

1. Go back to your repository tab in the browser
2. Click on the `_data` folder, then click `psychiana.csv`
3. Click the **History** button or the commit count
4. Click on your most recent commit
5. Look at the **diff**:
   - **Red** = deletion (old title)
   - **Green** = addition (new title)

This shows exactly what changed! Version control makes it easy to track edits to your metadata over time.

> [!TIP]
> **Want to explore more?** The [CollectionBuilder Metadata documentation](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/) has great examples of:
> - How to format dates for the timeline feature
> - How to add latitude/longitude for map points
> - How to use semicolons to separate multiple subjects
> - Best practices for writing descriptions

Wait for Mona to check your work! 🤖

> [!NOTE]
> **After syncing, come back to this Issue tab and refresh the page** (`Cmd+R` on Mac or `Ctrl+R` on Windows/Linux) if you don't see the next step appear within a minute or two.

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you're editing `_data/psychiana.csv`, not a different file
- The title field should be easy to spot—it's the second column
- Remember to **save the file** (`Ctrl+S` or `Cmd+S`) before staging changes
- If you make a mistake, you can undo (`Ctrl+Z` or `Cmd+Z`) before saving
- After syncing, the Source Control panel should show "0" changes
- If you accidentally broke the CSV structure, you can view the original on GitHub and copy it back

</details>
