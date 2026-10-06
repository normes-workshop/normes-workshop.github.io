# NORMES workshop website

A small GitHub Pages site. Jekyll turns the Markdown pages into HTML when
changes reach `main`. There is one shared template and no local setup is needed.

| File or folder | Purpose |
| --- | --- |
| `pages/index.md` | Series homepage at `/` |
| `pages/2026.md` | 2026 edition at `/2026/` |
| `files/` | Photos, PDFs and other downloads |
| `template/default.html` | Shared HTML and CSS |
| `_config.yml` | Jekyll configuration |

## Edit a page

Open a file in `pages/` on GitHub, click the pencil icon, edit it, and commit
the change to `main`. If you use a pull request, the change publishes after
the pull request is merged into `main`.

Each page starts with a small header:

```yaml
---
title: "NORMES 2026"
permalink: /2026/
---
```

`title` supplies the page heading and browser-tab title. Keep `permalink`
unchanged when editing an existing page. The template adds the main heading,
so use `##` for section headings in the text below the header.

Everything below the header is ordinary Markdown. For example:

```markdown
## Programme

**Monday:** opening talks and discussion.

- First session
- Second session

[Download the programme](/files/2026-programme.pdf)
```

Raw HTML is also supported. Ordinary edits need only the Markdown files;
leave the template and configuration alone.

## Add a photo or PDF

On GitHub, open `files/`, choose **Add file → Upload files**, and commit the
upload. Use filenames without spaces, such as `2026-city.jpg`.

Link to a PDF using `[Programme](/files/2026-programme.pdf)`.

Insert a photo using `![View of the hosting city](/files/2026-city.jpg)`,
or use HTML when you want a caption:

```html
<figure>
  <img src="/files/2026-city.jpg" alt="View of the hosting city">
  <figcaption>City name · Photo: photographer's name</figcaption>
</figure>
```

The photo automatically fits the page width. Add an appropriate description
in `alt` and the photo credit in the caption. `pages/2026.md` includes a
commented example: remove the surrounding `<!-- ... -->` after uploading
the photo, then edit its filename, description and credit.

Paths beginning with `/` work from both the homepage and edition pages.
Never link to `/pages/2026.md`; its public address is `/2026/`.

## Add an edition

1. Copy the contents of `pages/2026.md` into a new file, e.g. `pages/2027.md`.
   In GitHub's **Add file → Create new file**, enter `pages/2027.md` as the
   filename and paste the copied text.
2. Change the header to `title: "NORMES 2027"` and `permalink: /2027/`.
   Use a different permalink for every page.
3. Replace the text and photo reference. Upload any new files to `files/`.
4. Add `- [2027 edition](/2027/)` to the edition list in `pages/index.md`.
5. Commit the changes to `main`.

The new page uses the same template automatically. No configuration or
template changes are needed. Existing editions keep their URLs.

For a page in another language, optionally add `lang: fr` (or another language
code) to its header so the HTML declares the correct language.
