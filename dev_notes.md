# Dev Notes: Editing and Publishing Blog Posts

## Writing a new post

Create a file in `_posts/` with this naming convention:

```
_posts/YYYY-MM-DD-title-in-lowercase-with-hyphens.md
```

The date in the filename controls the publication date and sort order.

Start every post with front matter:

```markdown
---
layout: post
title: "Your Post Title Here"
category: "Learning by Inventing"
tags: [education, discovery, mathematics]
excerpt: >
  A one or two sentence summary shown in post cards and meta descriptions.
  Write this as if it is the opening hook of the essay.
---

Your post content starts here...
```

### Required fields

| Field | What it does |
|---|---|
| `layout` | Always `post` |
| `title` | Shown in the browser tab, post header, and cards |
| `category` | Controls filtering on the Essays page (must match exactly) |
| `excerpt` | Shown in post cards and SEO descriptions |

### Optional fields

| Field | What it does |
|---|---|
| `tags` | List of lowercase hyphenated tags |
| `featured: true` | Pins to the Featured Essays section on the homepage |
| `math: true` | Loads MathJax for LaTeX rendering in that post |
| `show_excerpt: false` | Hides the excerpt from the post header |

---

## The seven categories

Use one of these exactly — spelling and capitalisation matter for the essay filter:

```
AI and Human Thinking
Learning by Inventing
Building Terno AI
Agentic Systems
Founder Journey
Education and Careers
Beyond Common Sense
```

---

## Writing markdown

### Text

```markdown
Normal paragraph text.

**Bold**, _italic_, `inline code`.

> A blockquote appears with a blue left border and a light blue background.
```

### Links

```markdown
[Link text](https://example.com)                 — external link
[About page](/about/)                            — internal link
[Another post](/2025/10/01/some-post-title/)     — link to a post
```

### Code blocks

Specify the language for syntax highlighting:

````markdown
```python
def greet(name):
    return f"Hello, {name}"
```

```sql
SELECT category, SUM(revenue)
FROM sales
GROUP BY category
ORDER BY 2 DESC;
```
````

Supported: `python`, `javascript`, `sql`, `bash`, `yaml`, `json`, `ruby`, `html`, `css`, and most others.

### Mathematics

Add `math: true` to the front matter, then write LaTeX inline with `$...$` or display with `$$...$$`:

```markdown
---
math: true
---

The Pythagorean theorem states that $a^2 + b^2 = c^2$.

The loss function is:

$$L(\theta) = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$
```

### Lists

```markdown
- Unordered item
- Another item
  - Nested item

1. First step
2. Second step
3. Third step
```

### Images

Put images in `assets/images/` and reference them like this:

```markdown
![Description of the image](/assets/images/your-image.png)
```

---

## Previewing locally

You need Ruby 3.0+ installed. If you use Homebrew:

```bash
brew install ruby
gem install bundler
```

Then from the project directory:

```bash
bundle install        # first time only
bundle exec jekyll serve --livereload
```

Open `http://localhost:4000` in a browser. The site rebuilds automatically when you save a file. Stop the server with `Ctrl+C`.

If your system Ruby is too old (the default macOS Ruby 2.6 is), use rbenv:

```bash
brew install rbenv
rbenv install 3.2.0
rbenv local 3.2.0
gem install bundler
bundle install
```

---

## Publishing to GitHub Pages

### First time setup

1. Create a GitHub repository named `sandeepgiri.github.io`
2. Add the remote and push:

```bash
git remote add origin git@github.com:sandeepgiri/sandeepgiri.github.io.git
git push -u origin main
```

3. In the GitHub repo: **Settings → Pages → Source → GitHub Actions**

The site will build and deploy automatically. The first deploy takes about two minutes. Subsequent pushes deploy in under a minute.

### Publishing a new post

```bash
# Write your post in _posts/
git add _posts/2026-01-15-my-new-essay.md
git commit -m "Add essay: My New Essay Title"
git push
```

That's it. GitHub Actions picks up the push, builds the Jekyll site, and deploys it. No manual steps.

### Checking the build

Go to your repo on GitHub → **Actions** tab. You can watch the build run and see any errors there if the deploy fails.

---

## Updating existing content

### Edit a post

Open the file in `_posts/`, make changes, commit and push:

```bash
git add _posts/2025-10-01-learning-by-inventing-teaching-discovery.md
git commit -m "Update: fix typo in learning by inventing post"
git push
```

### Edit site config (title, links, social URLs)

Open `_config.yml`. The placeholder values that need filling in before launch:

```yaml
url: "https://sandeepgiri.github.io"   # your actual GitHub Pages URL

author:
  linkedin: "https://linkedin.com/in/your-handle"
  github:   "https://github.com/your-handle"
  twitter:  "your-twitter-handle"

cloudxlab_url: "https://cloudxlab.com"
terno_url:     "https://terno.ai"
```

After editing `_config.yml`, restart the local server (`Ctrl+C`, then `bundle exec jekyll serve`) because config changes are not picked up by live reload.

### Edit a static page

The pages are plain Markdown files in the root directory:

| File | Page |
|---|---|
| `about.md` | `/about/` |
| `learning-by-inventing.md` | `/learning-by-inventing/` |
| `terno-ai.md` | `/terno-ai/` |
| `projects.md` | `/projects/` |
| `contact.md` | `/contact/` |

Edit, commit, push. Same workflow as posts.

---

## Adding a profile photo

1. Save a square photo (recommended: 400×400 px) as `assets/images/profile.jpg`
2. In `about.md`, find the div with `SG` initials and replace it:

```html
<!-- Find this: -->
<div style="...font-size:2rem;color:#9CA3AF...">SG</div>

<!-- Replace with: -->
<img src="/assets/images/profile.jpg" alt="Sandeep Giri" style="width:100px;height:100px;border-radius:50%;object-fit:cover">
```

3. In `_layouts/post.html`, find the author bio card and replace the `SG` div similarly.

---

## Featuring a post on the homepage

Add `featured: true` to the post's front matter. The homepage shows up to 3 featured posts. If none are marked featured, it falls back to the 3 most recent posts.

```yaml
---
layout: post
title: "My Important Essay"
category: "AI and Human Thinking"
featured: true
---
```

---

## File structure reference

```
_posts/          ← all blog posts go here
_layouts/        ← page templates (don't edit unless changing the design)
_includes/       ← reusable HTML fragments (header, footer, post card)
_sass/           ← stylesheet source files
assets/css/      ← compiled CSS entry point (don't edit directly)
assets/images/   ← images
_config.yml      ← site settings
```
