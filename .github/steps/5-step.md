## Step 5: Customize Your Collection's Theme

Excellent! Your Psychiana collection is now live in your browser. Now let's customize the visual appearance and features using the `theme.yml` file!

### 📖 Theory: Theme Configuration in CollectionBuilder

CollectionBuilder separates visual/feature customization from site configuration:

- **`_config.yml`** - Core site settings (metadata source, title, URLs)
- **`_data/theme.yml`** - Visual customization and feature controls

The `theme.yml` file lets you control:
- **Home page**: Featured image, banner positioning
- **Browse page**: Search options, sorting
- **Subjects page**: Which fields to display, minimum counts
- **Map page**: Zoom level, base map style, clustering
- **Visual style**: Colors, fonts, Bootstrap themes

> [!TIP]
> Because `theme.yml` is NOT a Jekyll config file, changes appear immediately when you refresh your browser—no need to restart the server!

### ⌨️ Activity: Explore and Customize Theme Options

Let's make some visual changes and see them instantly!

**Part 1: Change the Featured Image**

The featured image appears on your home page. Let's pick a different image from the Psychiana collection.

1. Make sure Jekyll is still running from Step 4 (check the TERMINAL tab)
2. In your browser, go to your Psychiana collection home page
3. Look for the **Content** box on the bottom right of the page
4. Click the **"32 IMAGE"** link - this shows all 32 image items in the collection
5. Browse the images and pick one you like!
6. Click on an image to view its item page
7. Look at the URL - it will end with something like `/items/psychiana021.html`
8. The **objectid** is the part before `.html` (e.g., `psychiana021`)
9. Copy that objectid!

Now let's use it:

1. In VS Code, open `_data/theme.yml`
2. Find line 11: `featured-image: demo_033`
3. Change it to your chosen objectid (e.g., `featured-image: psychiana021`)
4. **Save the file** (`Ctrl+S` or `Cmd+S`)
5. **Refresh your browser** - you should see the new featured image immediately!

> [!TIP]
> The featured image is also used in social media previews when people share your collection!

**Part 2: Customize the Subjects Page**

The Subjects page shows a word cloud of topics. Let's customize how it works!

1. In `_data/theme.yml`, find the **SUBJECTS PAGE** section (around line 37)
2. Try these changes:
   - **Change `subjects-fields`**: Currently `subject;creator` - you could add more fields or remove one
   - **Change `subjects-min`**: Currently `1` - try `2` to only show subjects with 2+ occurrences
   - **Add stopwords**: Add `subjects-stopwords: Religion;Idaho` to hide those common terms
3. **Save the file** and **refresh your browser**
4. Click on the **Subjects** page to see your changes!

> [!NOTE]
> Learn more about all theme options in the [CollectionBuilder Theme Documentation](https://collectionbuilder.github.io/cb-docs/docs/theme/#theme-configuration-options).

**Part 3: Adjust the Map Settings**

The Psychiana collection includes location data. Let's customize the map!

1. In `_data/theme.yml`, find the **MAP PAGE** section (around line 52)
2. Try these changes:
   - **Change `zoom-level`**: Currently `5` - try `7` for a closer view, or `3` for further out
   - **Change `map-base`**: Try different options:
     - `Esri_WorldStreetMap` (default)
     - `Esri_NatGeoWorldMap` (National Geographic style)
     - `Esri_WorldImagery` (satellite view)
     - `OpenStreetMap_Mapnik` (OpenStreetMap style)
   - **Toggle `map-cluster`**: Change between `true` and `false` to see the difference in how map markers are grouped
3. **Save the file** and **refresh your browser**
4. Click on the **Map** page to see your changes!

**Part 4: Try a Bootswatch Theme (Then Remove It)**

CollectionBuilder uses Bootstrap for its base styling, and you can dramatically change the look with Bootswatch themes!

1. In `_data/theme.yml`, find the **BOOTSWATCH THEMES** section (around line 106)
2. Find the line: `bootswatch: # leave blank or comment out for plain bootstrap`
3. Try adding a theme name, like:
   - `bootswatch: cosmo` (clean and modern)
   - `bootswatch: darkly` (dark theme)
   - `bootswatch: flatly` (flat design)
   - `bootswatch: lumen` (light with nice typography)
   - `bootswatch: slate` (another dark option)
4. **Save and refresh** to see the dramatic visual change!

> [!IMPORTANT]
> **About Accessibility:** Some Bootswatch themes are **not accessible** for all users (they may have poor color contrast or other issues). CollectionBuilder is built with **accessibility as a priority**, using the default Bootstrap theme. Feel free to explore Bootswatch themes, but be aware of these limitations!

5. **Remove the Bootswatch theme** by either:
   - Deleting the theme name (leave `bootswatch:` blank)
   - Or commenting it out: `# bootswatch: cosmo`
6. **Save and refresh** to return to the accessible default theme

**Part 5: Explore More Options!**

The `theme.yml` file has many more options to explore:

- **Home banner positioning** (line 16): Change where the banner image appears
- **Advanced search** (line 23): Enable/disable advanced search features
- **Timeline settings** (line 66): Customize year navigation
- **Navbar colors** (line 98): Change the navigation bar colors
- **Custom fonts** (line 109): Add custom fonts from Google Fonts

Take a few minutes to experiment! Every change appears immediately when you refresh.

> [!TIP]
> The [Theme Configuration Documentation](https://collectionbuilder.github.io/cb-docs/docs/theme/#theme-configuration-options) explains every option in detail.

**Part 6: Commit Your Theme Changes**

Once you're happy with your customizations:

1. Open the **Source Control** panel
2. **Stage** `_data/theme.yml` by clicking the **+** button
3. **Write a commit message**: `Customize collection theme`
4. **Commit** and **Sync** to GitHub

Wait for Mona to check your work! 🤖

> [!NOTE]
> **After syncing, come back to this Issue tab and refresh the page** (`Cmd+R` on Mac or `Ctrl+R` on Windows/Linux) if you don't see the next step appear within a minute or two.

<details>
<summary>Having trouble? 🤷</summary><br/>

- **Changes not appearing?** Make sure you saved the file (`Ctrl+S` or `Cmd+S`)
- **Server stopped?** Restart it with `bundle exec jekyll serve`
- **Made a mistake?** Undo with `Ctrl+Z` or `Cmd+Z` before saving
- **Want to see original values?** Check the file on GitHub before your changes
- **Browser showing old version?** Try a hard refresh: `Ctrl+Shift+R` (Windows/Linux) or `Cmd+Shift+R` (Mac)
- YAML syntax matters: Keep the same spacing and indentation as the original

</details>
