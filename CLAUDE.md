# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

John Altidor's personal academic home page, served by GitHub Pages from the `master` branch (`jgaltidor.github.io`). It is a plain static site: no build step, no framework, no Jekyll config, no package manager, no tests, no linter. Pushing to `master` publishes it.

To preview locally, open `index.html` in a browser or serve the directory, e.g. `python3 -m http.server`.

## Structure

- `index.html` is the only page. It is hand-written XHTML 1.0 Transitional, indented with tabs, and organized into `<div>` sections by class: `header`, `research_interests`, `projects`, `refpubs` (refereed publications), `unrefpubs` ("Other Documents"), `teaching`, `awards`, `events`, `service`.
- `styles.css` is the single stylesheet. Classes used for content markup: `.pubtitle` (bold paper title), `.smallheading`, `.code` (inline monospace for type names like `List<E>`), `.prjtitle`/`.prjdesc` for projects.
- Papers, slides, and photos (`*.pdf`, `*.pptx`, `*.jpg`) sit at the repo root and are linked by relative path from `index.html`. Adding a publication means dropping the file at the root and adding an `<li>` to the `refpubs` or `unrefpubs` list, following the existing pattern: `.pubtitle` title, `(paper, slides)` links, `<br/>`, authors with `<em>John Altidor</em>`, `<br/>`, venue.
- `twelf_exercises/` holds Twelf (`.elf`) exercise files from a Twelf tutorial. Each subdirectory's `sources.cfg` lists the `.elf` files in load order. `starter_links.txt` gives the URLs students use, written relative to `<homepage>`.
- `plgroup/` and `spring13/` hold homework PDFs for past courses/reading groups.

Many external links in `index.html` point to old UMass/conference URLs that may no longer resolve. Leave them alone unless asked to update them.
