---
name: update-github-info
description: Draft Mona website updates from the GitHub Blog and GitHub Changelog.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before drafting updates.

Use these sources:
- `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Update `site/content/github-info.md` with concise, practical updates for readers and include source context whenever the content comes from the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use `safe-outputs` with `create-pull-request` so the agent can propose changes without writing directly to `main`.
