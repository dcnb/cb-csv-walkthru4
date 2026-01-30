# Claude/Agent Context for CollectionBuilder CSV Tutorial

This repository is a **GitHub Skills tutorial** that teaches users how to build a digital collection using CollectionBuilder-CSV. It uses GitHub's skills tutorial conventions with automated workflow triggers.

## Project Structure

### Core Tutorial Files

| Path | Purpose |
|------|---------|
| `.github/steps/0-welcome.md` | Initial welcome message posted to the Issue |
| `.github/steps/1-step.md` through `7-step.md` | Step-by-step tutorial content |
| `.github/steps/x-review.md` | Final review/congratulations content |
| `.github/workflows/0-start-exercise.yml` | Initiates the tutorial, creates Issue |
| `.github/workflows/1-step.yml` through `7-last-step.yml` | Workflow triggers for each step |
| `.github/course-details.json` | Tutorial metadata |

### How GitHub Skills Tutorials Work

1. User clicks "Use this template" to create their own repo
2. `0-start-exercise.yml` runs on first push, creates an Issue with welcome content
3. Each step workflow watches for specific file changes (paths trigger)
4. When triggered, workflow posts next step content as Issue comment
5. Workflows enable/disable each other sequentially

### Workflow Trigger Pattern

Each workflow:
- Watches specific file paths for changes
- Runs validation checks on the work
- Posts feedback and next step content to the Issue
- Disables itself and enables the next workflow

Example trigger:
```yaml
on:
  push:
    branches:
      - main
    paths:
      - '_config.yml'  # Triggers when this file changes
```

## Current Step Order & Triggers

| Step | Trigger File(s) | Activity |
|------|-----------------|----------|
| 0 | Push to main (any) | Create Issue, post Step 1 |
| 1 | `_config.yml` | Edit author field |
| 2 | `_data/psychiana.csv` | Explore & edit metadata (combined with old Step 3) |
| 3 | `_data/psychiana.csv` | Configure site for Psychiana |
| 4 | `_config.yml` | Configure metadata setting |
| 5 | `_data/theme.yml` | Preview collection, edit theme |
| 6 | `pages/about.md` | Customize About page |
| 7 | `_config.yml` | Publish to GitHub Pages |

## Key CollectionBuilder Concepts to Emphasize

### Metadata Fields (CSV)
- **Required**: `objectid`, `title`
- **Display control**: `display_template`, `object_location`, `image_small`, `image_thumb`
- **Visualizations**: `latitude`/`longitude` (map), `date` (timeline), `subject` (word cloud)

### Display Templates
Values: `image`, `pdf`, `video`, `audio`, `record`, `panorama`, `compound_object`, `multiple`

### Key Config Files
- `_config.yml` - Site-wide Jekyll settings
- `_data/theme.yml` - Theme options (featured-image, map settings, etc.)
- `_data/psychiana.csv` - Collection metadata

## Pending Changes/Notes

These notes from the maintainer should guide future edits:

### Step 0 (Welcome)
- ✅ Added note to refresh page and link to GitHub Skills

### Step 1 (Codespaces)
- ✅ Added navigation instructions (right-click Code button, open in new tab)
- ✅ Added "Having trouble" dropdown with Codespace link
- ✅ Added CB-Examples link to explore while waiting
- ✅ Added Part 6 to view diff on GitHub

### Step 2 (Metadata) - NEEDS COMPLETION
- Remove line about Excel/LibreCalc being alternatives
- De-emphasize `format` field (not required for CSV)
- Remove `filename` as required (not accurate for CSV)
- Focus on `display_template`, `object_location`, `image_small`, `image_thumb`
- Link to https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/#display-template
- Combine with Step 3 (old) - add activity to edit psychiana001 title
- Explain psychiana001 is a YouTube video from Northwest Public Broadcasting
- Note the title has commas so it's in quotes (CSV learning moment)
- Have them view the diff before committing

### Step 3 (old) - TO BE MERGED INTO STEP 2
- Content should merge into Step 2 to reduce redundancy

### Step 4 (Config) - NOW STEP 3
- Note that suggested values are just suggestions - users can customize!

### Step 5 (Preview) - SHOULD COME EARLIER
- Should come BEFORE the config changes step
- User sees demo data first, then makes changes
- Remove the `echo "Previewed collection locally" > .preview-complete` command (confusing)
- Add activity: Change `featured-image` in `theme.yml` to `demo_006`
- Have them explore Browse page ("32 IMAGE" link), grab objectid from URL
- Link to theme docs: https://collectionbuilder.github.io/cb-docs/docs/theme/#theme-configuration-options
- Have them also edit subjects section and map zoom in theme.yml

### Step 6 (About Page) - Rename/Reorder as needed
- Keep as-is mostly

### Step 7 (Publish) - LAST STEP
- Have them STOP the Codespace first (click Codespaces button at bottom, "Stop Codespace")
- Go back to Issue tab, right-click Code menu, open in new tab
- Note they're editing `_config.yml` via GitHub web interface (not Codespace)
- Click pencil to edit, commit changes button at top right

### Interim Comments ("Watching for progress")
- Add reminder to click "Sync Changes" button
- Add reminder to refresh page (`Cmd+R` / `Ctrl+R`)

## Workflow Issues to Fix

Many workflows may not be triggering properly. Check:
1. Workflow names match exactly in enable/disable commands
2. Path triggers match the files users actually edit
3. Workflows are initially disabled (except Step 0)

## External Documentation Links

- CollectionBuilder Docs: https://collectionbuilder.github.io/cb-docs/
- CSV Metadata: https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/
- Theme Options: https://collectionbuilder.github.io/cb-docs/docs/theme/
- CB Examples: https://collectionbuilder.github.io/cb-examples/
- GitHub Skills: https://skills.github.com/

## Demo Collection

The tutorial uses the **Psychiana Digital Collection** from University of Idaho Library.
- Full collection: https://www.lib.uidaho.edu/digital/psychiana/
- Item `psychiana001`: YouTube video from Northwest Public Broadcasting about Psychiana
- Item `demo_006`: An image item good for featured-image examples
