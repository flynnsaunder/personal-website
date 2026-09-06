# Flynn Saunder — personal website

Plain HTML and one CSS file. No build step, no frameworks, no dependencies.
GitHub Pages serves the files exactly as they are in this repo.

## What each file is

| File / folder | What it's for |
|---|---|
| `index.html` | The homepage: intro, project list, resume, footer. |
| `assets/style.css` | All styling for every page. Edit once, changes everywhere. |
| `assets/headshot.jpg` | Your photo. Square. (Currently a placeholder `.svg`.) |
| `assets/resume.pdf` | Your CV, linked from the homepage. (Currently a placeholder.) |
| `projects/_template.html` | Copy this to start a new project page. |
| `projects/example-project.html` | A finished example — look here for how tags work. |
| `projects/images/` | Every image used on a project page lives here. |

You edit everything on **github.com** in the browser. When you commit a change,
GitHub rebuilds the site in about a minute.

---

## How to add a new project

### 1. Create the page

1. On github.com, open `projects/_template.html`.
2. Click the **Raw** button, select all, copy.
3. Go back to the `projects/` folder → **Add file ▸ Create new file**.
4. Name it with no spaces, ending in `.html` — e.g. `fsae-suspension.html`.
   This name becomes the web address: `.../projects/fsae-suspension.html`.
5. Paste. Then change the parts marked `CHANGE:` and write your project
   between the `WRITE YOUR PROJECT BELOW` markers.
6. Scroll down, **Commit changes**.

You only ever need these building blocks inside `<div class="project-body">`:

```html
<p>A paragraph of text.</p>

<h2>A section heading</h2>

<img src="images/my-photo.jpg" alt="what the photo shows">

<figure>
  <img src="images/my-photo.jpg" alt="what the photo shows">
  <figcaption>A caption under the photo.</figcaption>
</figure>

<ul>
  <li>A bullet</li>
  <li>Another bullet</li>
</ul>
```

Copy a block, change the words, repeat. That's the whole system.

### 2. Add the images

1. Open the `projects/images/` folder on github.com.
2. **Add file ▸ Upload files**, drag your photos in, **Commit changes**.
3. Reference them in your project page as `images/thefilename.jpg`.

Keep photos reasonably sized (roughly 1200–1600 px wide, under ~500 KB each)
so pages stay fast. Rename files to something clear before uploading, e.g.
`fsae-rig-test.jpg`.

### 3. Link it from the homepage

1. Open `index.html`, click the pencil to edit.
2. In the **SELECTED PROJECTS** section, copy one `<div class="list-item">`
   block and change the link, title, year and description:

```html
<div class="list-item">
  <div class="item-header">
    <span class="item-title"><a href="projects/fsae-suspension.html">FSAE Suspension Rig</a></span>
    <span class="item-date">2026</span>
  </div>
  <p class="item-desc">One sentence about it for the homepage list.</p>
</div>
```

3. **Commit changes.** Wait ~1 minute, refresh your site.

---

## How to update your resume

**On the homepage:** open `index.html`, find the **RESUME & EXPERIENCE**
section, and copy/edit the `<div class="list-item">` blocks — same pattern as
projects. Newest role at the top.

**The PDF:** upload your CV as `assets/resume.pdf` (Add file ▸ Upload files,
into the `assets/` folder, keep the name `resume.pdf` so the link keeps working).

---

## How to change your photo

Upload a **square** image as `assets/headshot.jpg` into the `assets/` folder.
Then in `index.html` change this one line:

```html
<img class="headshot" src="assets/headshot.svg" alt="Flynn Saunder">
```

to `src="assets/headshot.jpg"`. If the photo isn't perfectly square the CSS
crops it to a square automatically — it just crops from the centre, so pick
one where your face is roughly centred.

---

## Your email

The footer builds `flynnsaunder@icloud.com` with a few lines of JavaScript so
that bots scraping the raw HTML never see the full address. Nothing to maintain.
To change it, edit the `user` and `domain` lines in the `<script>` at the
bottom of `index.html`.

---

## Removing the example

Once you've added a real project, delete `projects/example-project.html` and
its line in `index.html`. Keep `projects/_template.html` — that's your starting
point every time.

---

## Previewing changes before publishing (optional)

You don't need this — committing on github.com and waiting a minute is fine.
But if you ever want to check locally: open the folder and double-click
`index.html` to open it in your browser. Project pages and styling will all
work because there's no build step.
