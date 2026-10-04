# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

John Altidor's personal academic home page, served by GitHub Pages from the `master` branch (`jgaltidor.github.io`). It is a plain static site: no build step, no framework, no package manager, no tests, no linter. Pushing to `master` publishes it. GitHub Pages still runs Jekyll over the repo, so `_config.yml` excludes `README.md` and `CLAUDE.md` from the published site; add any other repo-only Markdown files there too.

To preview locally, open `index.html` in a browser or serve the directory, e.g. `python3 -m http.server`. Check that the page is still well-formed with `xmllint --noout index.html`.

## Structure

- `index.html` is the only page. It is hand-written XHTML 1.0 Transitional, indented with tabs, and organized into `<div>` sections by class: `header`, `research_interests`, `projects`, `refpubs` (refereed publications), `unrefpubs` ("Other Documents"), `teaching`, `awards`, `events`, `service`.
- `styles.css` is the single stylesheet, a dark theme. The header photo floats right and is not cleared until the end of `.research_interests`, so Research Interests wraps beside the photo; the `overflow: hidden` on that section's `h2` keeps its rule from running under the photo. Classes used for content markup: `.pubtitle` (bold paper title), `.smallheading`, `.code` (inline monospace for type names like `List<E>`), `.prjtitle`/`.prjdesc` for projects.
- Papers, slides, and photos (`*.pdf`, `*.pptx`, `*.jpg`) sit at the repo root and are linked by relative path from `index.html`. Adding a publication means dropping the file at the root and adding an `<li>` to the `refpubs` or `unrefpubs` list, following the existing pattern: `.pubtitle` title, `(paper, slides)` links, `<br/>`, authors with `<em>John Altidor</em>`, `<br/>`, venue. Exception: the type theory tutorial paper and its two slide decks are published as GitHub Release assets of their own repos (`typetheory_paper`, `typetheory_slides`, `twelf_slides`), so `index.html` links to `https://github.com/jgaltidor/<repo>/releases/latest/download/<repo>.pdf` instead; the old copies at the root (`typetheory_paper.pdf`, `typetheory_slides.pdf`, `twelf_slides.pdf`) are kept only so outside links to them keep working.
- `twelf_exercises/` holds Twelf (`.elf`) exercise files from a Twelf tutorial. Each subdirectory's `sources.cfg` lists the `.elf` files in load order. `starter_links.txt` gives the URLs students use, written relative to `<homepage>`.
- `plgroup/` and `spring13/` hold homework PDFs for past courses/reading groups.

Many of the original UMass and conference pages are gone, so most old links point to Wayback Machine snapshots (`https://web.archive.org/web/<timestamp>/<original-url>`). When fixing a broken link, use a snapshot from around the relevant date and check it loads. The CV repo at `~/Documents/mywork/projects/writing/jga_cv_prj/jga_cv` links many of the same pages; reuse its URL when it has one so the two stay consistent.
