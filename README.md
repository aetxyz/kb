# kb

> Simple local archiving & web note-taking tool

`kb` was born out of my desire to conveniently download & store web pages (to
fight linkrot), and also to store my own thoughts & notes about them alongside
them.

It is a simple shell script that takes a single argument, a URL, and places it
in a location according to its domain and path within a subdirectory specified
by `KB_BASE_PATH` in env.

Once it downloads the web page, it opens `EDITOR` on a `_notes.md` file, which
is placed alongside the HTML file. You can optionally pass `-c` to skip this.

`kb` performs downloads using [monolith](https://github.com/Y2Z/monolith) and
tries to keep file size down by skipping audio & web fonts. It also skips all
JavaScript to avoid pages phoning home (most notably for this author,
[LessWrong](https://lesswrong.com) doesn't do great when downloaded with
`monolith` without this) at the cost of some pages not working correctly. But
`kb` is designed to preserve written text more than complex web pages. You can
always edit the script yourself, of course.

## Requirements

- [monolith](https://github.com/Y2Z/monolith)
- `EDITOR` set to your preferred CLI editor (e.g. `vim`, `nano`, `hx`)
- `KB_BASE_PATH` set to your top-level archive directory path

## Usage

```bash
kb 'https://www.lesswrong.com/s/5uZQHpecjn7955faL/p/X3HpE8tMXz4m4w6Rz'
```
