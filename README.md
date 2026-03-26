# Adam Aderram — Developer Portfolio

A personal portfolio website built to showcase my projects, skills, and experience as a software engineering student.

🌐 **Live site**: [ad25aderram.github.io/my-portfolio](https://AD25aderram.github.io/my-portfolio/)

---

## How I Built This

I started from the **HugoBlox Dev Portfolio template** and customized it to reflect my own profile, projects, and style.

### Customization steps

1. **Forked the HugoBlox Dev Portfolio template** from GitHub
2. **Updated personal info** — name, bio, avatar, and social links in `data/authors/me.yaml`
3. **Added my own projects** — each project has its own page under `content/projects/`
4. **Configured the tech stack section** with the tools and languages I actually use
5. **Filled in the experience & education timeline** in `content/_index.md`
6. **Tweaked the theme and colors** via `config/_default/params.yaml`
7. **Deployed to GitHub Pages** using the built-in GitHub Actions workflow

---

## Tech Stack

| Tool | Purpose |
|---|---|
| [Hugo](https://gohugo.io/) | Static site generator |
| [HugoBlox](https://hugoblox.com/) | Template & component framework |
| [GitHub Pages](https://pages.github.com/) | Free hosting & deployment |
| GitHub Actions | Automated build & deploy pipeline |

---

## Sections

- **Hero / About me** — who I am and what I'm working towards
- **Projects** — my personal and academic projects with tags and descriptions
- **Skills / Tech stack** — languages, frameworks, and tools I work with
- **Experience & Education** — my academic and professional timeline
- **Blog** — writeups, learnings, and notes
- **Contact** — ways to reach me

---

## Project Structure

```
my-portfolio/
├── config/_default/     # Site config, theme, and params
├── content/             # All page content (Markdown)
│   ├── _index.md        # Homepage sections
│   ├── projects/        # Individual project pages
│   └── blog/            # Blog posts
├── data/authors/        # Author profile (me.yaml)
├── assets/media/        # Images and media
└── static/uploads/      # Uploaded files
```

---

## Run Locally

```bash
# Install Hugo (extended version)
# https://gohugo.io/installation/

git clone https://github.com/AD25aderram/my-portfolio.git
cd my-portfolio
hugo server
```

Then open `http://localhost:1313` in your browser.

---

## Deployment

This site is deployed automatically to GitHub Pages on every push to `main` via GitHub Actions (`.github/workflows/deploy.yml`). No manual steps needed after a push.

---

MIT © Adam Aderram
