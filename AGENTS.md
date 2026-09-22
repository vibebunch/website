# AGENTS.md

Instructions for AI coding agents working in this repository. Read this before making
changes.

## What this repository is

The source of vibebunch.com, the website for a vibe coding group in Longmont and Boulder,
Colorado. The group mixes complete beginners with experienced developers, and the site is
deliberately built so that a beginner can change it from the GitHub web editor without
installing anything.

## This repository is public

Everything here is readable by anyone on the internet, including the full git history,
commit messages and branch names. Publishing is a one way door, because making the
repository private later does not reach copies other people already have.

**Never commit any of the following:**

- street addresses, including the address of whoever is hosting a meeting
- phone numbers, email addresses or full names beyond a first name
- screenshots or images containing any of the above
- anything copied out of the `clubhouse` repository
- API keys, tokens or passwords of any kind

When adding a meeting to the site, use the town only. Longmont or Boulder. The exact
address reaches members through the group chat and never through this repository.

If a task seems to require any of the above, stop and say so rather than finding a way
around it.

## Do not add a build step

This site is plain HTML and CSS on purpose. It has no package manager, no bundler and no
framework, and it must stay that way.

**Do not introduce** npm, React, Vue, Svelte, Tailwind, Vite, webpack, TypeScript, Sass, a
static site generator, or a CI step that compiles anything. Do not add a `package.json`.

The reason is not taste. Every one of those turns a one click edit in the browser into a
local toolchain install, which locks out exactly the people this group exists to include.
A site a beginner cannot edit has failed at its job, however clean the code is.

If a task genuinely cannot be done without a build step, say so and explain the tradeoff
rather than quietly adding one.

## Keep it readable rather than clever

- Keep the files flat. No component extraction, no templating, no shared partials.
- Prefer a little repetition over an abstraction. Someone copying an existing block to add
  their project is the intended way to use this site.
- Leave the comment markers in `index.html` that show where to add a meeting or a project.
- Plain CSS in `style.css`. Keep the light and dark themes both working, and keep the
  layout usable on a phone.

## Ask before touching these

- **`CNAME`** holds the custom domain. Deleting or changing it takes the site offline.
- **`.github/workflows/`** controls publishing.
- Anything to do with DNS, which lives outside this repository entirely.

## How changes land

Branch and pull request, never a direct commit to `main`. Write the pull request
description in plain language, because the reviewer may be someone who started coding last
month.

## Files

| File | Purpose |
|---|---|
| `index.html` | Front page. Meetings and the project gallery live here. |
| `whats-public.html` | Live view of which organization repositories the public can see. Calls the GitHub API anonymously on purpose, so it shows what a stranger sees. Do not add authentication to it. |
| `style.css` | All styling. |
| `CNAME` | The custom domain. |
