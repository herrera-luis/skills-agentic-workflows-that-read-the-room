---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
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
    - github.com
    - github.blog
    - awesome-copilot.github.com
engine:
  id: copilot
  copilot-sdk: true
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use web-fetch for external public guidance and these official sources:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Use GitHub repository API tools to read repository guidance or reference files. Do not use terminal, CLI, or sandboxed commands to read those files or fetch public web pages.

Update `site/content/github-info.md` with concise, practical, verifiable updates. Include source context for content drawn from the GitHub Blog or GitHub Changelog, and do not invent details.

Open a draft pull request for Mona to review, using a title that mentions Mona or GitHub Info. Do not write directly to `main`; use the configured `safe-outputs` `create-pull-request` capability.
