# Android / Termux guide

This guide prepares an Android phone to run OmniRoute headlessly. Follow upstream project instructions and confirm the installed Node version before proceeding.

## 1. Install Termux

Install Termux from a trusted official source:
- [Termux GitHub releases](https://github.com/termux/termux-app/releases)
- [Termux F-Droid page](https://f-droid.org/packages/com.termux/)

Do not install random APK mirrors. Open Termux and run:

    pkg update
    pkg upgrade
    pkg install nodejs-lts python build-essential git
    node --version
    npm --version

OmniRoute's supported Node ranges are documented in its package metadata/upstream Termux guide. If Termux LTS is outside the supported range, use the version recommended by the current upstream guide rather than forcing an install.

## 2. Get OmniRoute source and inspect

    git clone https://github.com/diegosouzapw/OmniRoute.git
    cd OmniRoute

Before running any install script, review README and package scripts:

    cat README.md
    node -e "const p=require('./package.json'); console.log(JSON.stringify({engines:p.engines,scripts:p.scripts},null,2))"

Then follow the current upstream Termux guide for exact dependency/install/start commands:
[OmniRoute Termux Guide](https://github.com/cheaper-inference/OmniRoute/wiki/Termux-Guide)

The Electron desktop app is not supported in Termux; use the headless server and web dashboard/API.

## 3. Keep it local and secure

- Bind dashboard/API to loopback unless remote access is deliberately configured.
- Do not expose API to the public internet without authentication and network protections.
- Never put provider keys in this GitHub repository.
- Use OmniRoute's official dashboard/configuration flow for provider keys.
- Do not paste secrets into chat or terminal commands that may be saved in shell history.

## 4. Native Claude Code on Termux (separate option)

A community-maintained project, [claude-code-android](https://github.com/ferrumclaudepilgrim/claude-code-android), documents running Anthropic's Linux ARM64 Claude Code binary on aarch64 Termux using glibc-runner. This is not an Anthropic-supported Android installation. Its installer downloads a large binary and installs additional packages; inspect the current script and project security notes before deciding whether to use it.

This route still requires a legitimate Claude subscription or Anthropic Console/API access. It does not unlock Claude Pro for free and does not make an official Claude login reusable through OmniRoute. Prefer the official Claude Code installation path on a supported OS where possible.

## 5. Free Claude Code (FCC) status

FCC's upstream README currently documents an installer for macOS/Linux and Windows, not a confirmed Termux/Android native install. The current upstream `pyproject.toml` pins Python to exactly `3.14.10`; its dependency set includes native packages (for example `grpcio` and `tiktoken`). Termux/Android wheel and build compatibility is therefore unverified and may fail even though Termux has Python and `uv`. Do not run the installer blindly or assume that a generic Linux install path works on Android.

Do not run the upstream install command blindly on Android. First inspect the current upstream installer and verify Termux compatibility:
[Free Claude Code README](https://github.com/Alishahryar1/free-claude-code)

If FCC is not supported in Termux, use a compatible Linux/cloud environment or another client supported by OmniRoute. Do not assume that setting an API base URL alone completes setup; the client must support the provider protocol and authentication.

## 6. Working with several repositories

Use GitHub's mobile app/browser to open the desired project repository, then use a supported coding environment to clone that project's repository. This workbench is a registry and guide, not a monorepo for all project code.
