# AGENTS.md

## Cursor Cloud specific instructions

### Repository status: planning stage (no application code yet)

This repository currently contains only `README.md` — a Vietnamese-language vision /
planning document for a planned web app that will offer multiple-choice math and English
practice exercises for elementary school students. As of this writing there is:

- No application source code.
- No dependency manifests or lockfiles (no `package.json`, `requirements.txt`, etc.).
- No build, test, lint, or run configuration.
- No services to start.

Because of this, **there is nothing to install, build, run, or test**, and the update
script is intentionally a no-op until code is added.

### Toolchain available in the VM

The base image already provides the languages the README lists as candidate stacks:

- Node.js (`node`, `npm`) — for a future React/Vue/Node.js frontend or backend.
- Python 3 (`python3`, `pip3`) — for a future Django backend.

No language-version files (`.nvmrc`, `.python-version`, etc.) exist, so the system
defaults are used.

### When application code is added

The configured update script auto-detects manifests and installs dependencies:

- Node: runs `pnpm install` / `yarn install` / `npm ci` / `npm install` depending on the
  lockfile/manifest present.
- Python: runs `pip3 install -r requirements.txt` if that file exists.

If a different stack or package manager is chosen, update both the update script and this
section accordingly. Standard run/build/test commands should live in the project's
`package.json` scripts, `Makefile`, or framework tooling once they exist — reference those
instead of duplicating them here.
