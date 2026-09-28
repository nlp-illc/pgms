# Use this template

1. Create your github (public) repo `COURSE` (you pick the name, ofc) within `nlp-illc`.
2. Download the content of this repo (but not its git history; either download a zip file, uncompress it, then recursive-copy all of the files and directories into your own new repo, or do it via command line as in the example below).
3. Edit `_config.yaml` (esp the attribute `baseurl` which should be the same as your new repo's name); and edit everything else that's relevant (see the rest of the README). 

Example

```bash
# Clone the template repository into a new directory
git clone https://github.com/nlp-illc/course.git COURSE

# Enter the new project
cd COURSE

# Remove the template repository's Git history
rm -rf .git

# Start a new, independent Git repository
git init
git add .
git commit -m "Initial commit from template"

# Create an empty repository named `COURSE` on GitHub, then connect it
git branch -M main
git remote add origin https://github.com/nlp-illc/COURSE.git
git push -u origin main
```

# Add a root page

Root pages are for whatever concerns `COURSE` generally (e.g., about, blog, past editions, etc.). Most likely you don't need root pages, rather you should work with specific editions (e.g., 2026 or 2027) which are hosted under their respective folders (e.g., `./2026/` or `./2027/`); for that, see the next section.

Suppose you want to add a root page such as `./about.md`, here's the necessary preamble
```
---
layout: page
title: About
ref: about
permalink: /about/
---
```
The field `ref` is for the menu in the site's header. You will also need to change `header_page_refs` in `_config.yaml` to suit your needs. 

# Add a new edition

Let's suppose the new edition runs in some `YEAR`.

Create a folder `./YEAR` and add `./YEAR/index.md` with the preamble
```
---
layout: home
title: COURSE YEAR
permalink: /YEAR/
---
```
Then update the root's `./index.html` to redirect to the new edition.

To keep things simple, use `./YEAR/index.md` for everything you need. To ease navigation, you can have a neat navigation bar within the site's banner, simply add something like the following to the preamble:
```
menu:
- Syllabus
- Team
```
where `Syllabus` and `Team` are Markdown section headers within `./YEAR/index.md`.
Of course, if you need to have additional pages, you can have them, but follow the instructions in the subsection below.

Last, update `./past.md` with a link to the older edition. If YEAR is 2027, then perhaps you add something of the kind:
```markdown
Previous editions: [2026]({{ '/2026/' | relative_url }})
```


## Other pages within the new edition

For other md files in the new edition's folder, such as `./YEAR/syllabus.md`, use the preamble
```
---
layout: default
title: Syllabus
permalink: /YEAR/syllabus/
tagline: YEAR
---
```
The `tagline` will remind anyone navigating the site that they are in the right edition (without them having to check their browser's address bar). 

Note that when linking to this, for example from `./YEAR/index.md`, paths are relative eg `[detailed program](./syllabus)`.

# Credit

This site uses the Cayman theme

[![Gem Version](https://badge.fury.io/rb/jekyll-theme-cayman.svg)](https://badge.fury.io/rb/jekyll-theme-cayman)

*Cayman is a Jekyll theme for GitHub Pages. You can [preview the theme to see what it looks like](http://pages-themes.github.io/cayman), or even [use it today](#usage).*


