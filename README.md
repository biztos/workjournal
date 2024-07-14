# Work Journal

A command-line utility for keeping a work (or any) journal.

It's a good idea to keep track of your work as you go along.  Work Journal
helps you do that, with a focus on "write now grep later."  You can edit any
file, but you usually just add more.

Inspired by this Hacker News article:

https://news.ycombinator.com/item?id=40950584

## The Basic Idea

### All-in-one CLI: `wj`

### Additive process: by default, adds files.

```bash
$ wj foobar
$ cat workjournal/my-project/20240714/0001.md
# ...TBD but probably something like frontmatter...
foobar
$
```

### Strong lookup: greppable etc etc.

```bash
$ wj find foobar
My Project: 20240714.0001: foobar
```
- -t for tags
- -a for all projects
- -d for date limit or just enter a date
- -e for exact string match
- ...and so on

### Native (extended) Markdown

...probably with metadata frontmatter.  Markdown flavor TBD, probably depends
on the tooling.

Idea: frontmatter database in SQLite3 holding all the above.

(OK, devil's advocate here: what exactly do I want from frontmatter that I
can't have from just autosetting a few tags?)

### Tag support: anything outside of code blocks `#tagged` is a tag.

Maybe a formatter so format-on-save sticks all the tags into the frontmatter?

### Integrates with standard UNIX tools.

- Want to use `grep` for `wj find` but still keep some flags? Can do!
- Etc... what else?

## Open Questions

- Build in go or build in Rust?

## Features

- Config with defaults.
- Init function, `wj init my-project`
- Git integration so you don't have to do that separately
	- E.g. I want to commit everything when added, but push when I say.
- TBD, more backlog...

## MVP Features

* Add (`wj add foobar`)
* Edit with $EDITOR (`wj add`)
* Edit last (`wj edit --last`)
* Edit specific (`wj edit path/to/file`)
* Look stuff up grep-ishly, TBD (`wj find foobar`)
* Very simple HTTP browser for stuff.
