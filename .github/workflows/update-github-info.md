---
name: update-github-info
description: Draft website updates for Mona's GitHub Info website from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '0 10 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[Mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit: {}
  web-fetch: {}
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info

Read `notes/mona-notes.md` before making any changes.

Use these sources to update `site/content/github-info.md`:
- Mona's internal notes: `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- awesome-copilot workflows: https://awesome-copilot.github.com/workflows/

Use web fetch to read:
- https://awesome-copilot.github.com/workflows/
Include workflow examples and source context from the Awesome Copilot page when relevant.

Update `site/content/github-info.md` with concise, accurate information for readers.
Include a new section titled `## Latest GitHub Updates` if one does not already exist.
When content comes from the GitHub Blog or GitHub Changelog, cite the source clearly.

Open a pull request for Mona to review. Use `safe-outputs` with `create-pull-request` so the agent can propose the patch without writing directly to `main`.
Make sure the pull request title mentions Mona or GitHub Info.

