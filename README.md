# NORMES workshop website

A small GitHub Pages site. Jekyll turns the Markdown pages into HTML when
changes are pushed to `main`. 

| File or folder | Purpose |
| --- | --- |
| `pages/index.md` | Homepage published at `/` |
| `pages/xxx.md` | Page published at `/xxx/` |
| `files/` | Photos, PDFs and other downloads |
| `template/default.html` | Shared HTML and CSS |
| `_config.yml` | Jekyll configuration |

## Edition of the site

Edit only the content of `pages` and `files`.

### Editing pages

- To edit a page directly on GitHub, open the corresponding `.md` file, click the pencil icon, edit it, and commit the change to `main`. (If you use a pull request, the change publishes after the pull request is merged into `main`.)
- You can also clone the Git repository on your local computer, commit changes locally and push them.

Pages are formatted in [https://www.markdownguide.org/cheat-sheet/](Markdown). HTML elements can be inserted in the Markdown. (The template adds the main heading, so use `##` for section headings in the text below the header.)

Each page starts with a small header:

```yaml
---
title: "NORMES 2026"
permalink: /2026/
---
```

`title` supplies the page heading and browser-tab title. Keep `permalink`
unchanged when editing an existing page. 

### Adding files

- Directly on GitHub, open `files/`, choose **Add file → Upload files**, and commit the
upload. Use filenames without spaces, such as `2026-city.jpg`.
- You can also clone the Git repository on your local computer, commit changes locally and push them.

Insert a photo using `![View of the hosting city](/files/2026-city.jpg)`,
or use HTML when you want a caption:

```html
<figure>
  <img src="/files/2026-city.jpg" alt="View of the hosting city">
  <figcaption>City name · Photo: photographer's name</figcaption>
</figure>
```

The photo automatically fits the page width. Add an appropriate description
in `alt` and the photo credit in the caption. 

### Add a page (e.g. for a new edition of the workshop)

1. Copy the contents of `pages/2026.md` into a new file, e.g. `pages/2027.md`.
   In GitHub's **Add file → Create new file**, enter `pages/2027.md` as the
   filename and paste the copied text.
2. Change the header to `title: "NORMES 2027"` and `permalink: /2027/`.
   Use a different permalink for every page.
3. Replace the text .
4. Add `- [2027 edition](/2027/)` to the edition list in `pages/index.md`.
5. Commit the changes to `main`.

The new page uses the same template automatically. No configuration or
template changes are needed. Existing editions keep their URLs.

For a page in another language, optionally add `lang: fr` (or another language
code) to its header so the HTML declares the correct language.
