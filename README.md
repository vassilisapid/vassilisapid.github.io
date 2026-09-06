# Vassilis Apidopoulos — Academic Pages starter content

This folder contains a starter migration of the current `vassilisapid.github.io` homepage into the structure used by the Academic Pages Jekyll template.

It is meant to be copied into a fork or template-created copy of `academicpages/academicpages.github.io`, not used as a complete standalone website theme.

## Recommended workflow

1. Create or fork the Academic Pages site into the existing GitHub Pages repository `vassilisapid.github.io`.
2. Copy the folders/files from this starter pack into the root of that repository.
3. Copy the existing binary assets from your old repository:
   - `photoVassi.jpg` → `images/photoVassi.jpg`
   - `CV_VassEN.pdf` → `files/CV_VassEN.pdf`
   - `ArchimedesIm.png` → `images/ArchimedesIm.png` if you still want to use the logo.
4. Commit and push.
5. In GitHub repository settings, check that Pages builds from the correct branch.

## What is included

```text
_config.yml
_data/navigation.yml
_pages/about.md
_pages/publications.md
_pages/talks.md
_pages/teaching.md
_pages/other.md
_pages/contact.md
_pages/cv.md
_publications/*.md
_talks/*.md
_teaching/*.md
_layouts/home-flex.html
_includes/head/custom.html
images/README.md
files/README.md
```

## Homepage layout switch

The homepage currently uses the standard Academic Pages sidebar profile, which is the simplest portrait-style layout.

In `_pages/about.md`, the relevant front matter is:

```yaml
author_profile: true
profile_variant: portrait
```

To switch to a wider top/landscape-style overview, change it to:

```yaml
author_profile: false
profile_variant: landscape
```

The custom layout `_layouts/home-flex.html` and CSS in `_includes/head/custom.html` implement this switch.

## Adding future entries

Add one Markdown file per item:

```text
new paper     → _publications/YYYY-title.md
new talk      → _talks/YYYY-MM-title.md
new teaching  → _teaching/YYYY-course.md
```

The list pages sort these entries automatically by date.

## Notes

- Month-only dates from the old webpage are stored as the first day of the month for sorting.
- The displayed text keeps the original month/year wording in each entry body where useful.
- The contact email is kept obfuscated, as in the old site.
- The binary image and PDF files are not included in this package; copy them from the current repository.
