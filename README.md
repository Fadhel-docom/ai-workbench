# AI Workbench

A shared workspace for using AI coding tools across multiple projects. This repository is intentionally project-agnostic.

## What this repo is

- A safe home for setup notes, reusable prompts, and project registry.
- A starting point for Android/Termux workflows with OmniRoute and Free Claude Code (FCC).
- Not a place to store API keys, access tokens, passwords, or private project source code.

## Android setup

OmniRoute documents a headless Termux setup. See [docs/android-termux.md](docs/android-termux.md).

**Important compatibility note:** OmniRoute supports Android/Termux as a headless server. FCC's upstream installer documents macOS/Linux/Windows, not Android/Termux specifically. FCC on Termux is therefore not guaranteed.

## Project registry

Add the repositories you use to [projects.md](projects.md). Keep this list free of credentials. Open a project repository separately in your coding agent; do not combine unrelated projects in this repo.

## Security

- Never commit .env files, API keys, OAuth tokens, private keys, or account cookies.
- Keep provider credentials in the local app/configuration UI or local environment only.
- Review upstream installation scripts before running them.
- Use minimum repository permissions.
- Public repository contents are visible to everyone.

## Upstream projects

- [Free Claude Code](https://github.com/Alishahryar1/free-claude-code)
- [OmniRoute website](https://omniroute.online/)
- [OmniRoute source](https://github.com/diegosouzapw/OmniRoute)
- [OmniRoute Termux guide](https://github.com/cheaper-inference/OmniRoute/wiki/Termux-Guide)

## License

Documentation and starter configuration in this repository are MIT-licensed. Upstream tools retain their own licenses.
