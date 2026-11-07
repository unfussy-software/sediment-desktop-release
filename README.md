# Sediment

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.png">
  <img src="assets/hero.png" width="1120" alt="In a terminal on the left, someone asks an agent to brief a podcast episode and file it on shelf; the agent runs sediment shelf and sediment add, then confirms the page is on the shelf, tagged brief. On the right, the Sediment window shows the shelf's list with that same page selected and open for reading.">
</picture>

**Agents write. You read. Sediment is the shelf between.**

Your agent files each page with one command: a brief, a research report,
a dashboard, a plan. You read them all in one place, on your Mac.

- **Local-first.** The shelf is a folder on your disk, and the app is a view
  over it. No account, nothing tracked, and any folder sync works with it.
- **Keyboard-driven.** Every common action is a chord away, and the chords
  match the Mac you already know.
- **Agent-native.** Say "file it on shelf" in your own words. Your agent
  files, tags and revises pages for you.

More at [unfussy.software/sediment](https://unfussy.software/sediment).

## Install

Sediment is in beta and needs macOS 26.0 or later.

1. Download `Sediment-<version>.dmg` from the
   [latest release](https://github.com/unfussy-software/sediment-desktop-release/releases/latest).
2. Open it and drag Sediment into your Applications folder.
3. Launch Sediment and choose the folder your shelf will live in. Any folder
   works, including one that iCloud Drive, Dropbox or OneDrive syncs.

Signed and notarized. Sediment updates itself; see what changed in the
[changelog](https://unfussy.software/sediment/changelog).

## Connect an Agent

Agents file to Sediment from wherever they run; where one runs decides how
it connects.

### In a Terminal

Claude Code, Codex CLI and other terminal agents use the `sediment`
command. Link it once from Sediment’s Settings ▸ Terminal, then install the
skill, so the agent knows how to file, find and edit there:

```
npx skills add unfussy-software/sediment-skills -g
```

### In a Desktop App

ChatGPT, Claude Desktop and other desktop apps reach Sediment through its
MCP server. Paste this into a new conversation; the agent sets the server
up the way its own app does, asks you for anything only you can do, and
confirms when it works:

```
Connect this app to Sediment, the app on my Mac that keeps my HTML pages
on a shelf. It offers an MCP server over stdio:

  command:    /Applications/Sediment.app/Contents/Helpers/sediment
  arguments:  mcp

If it isn’t at that path, find the app by its bundle id,
com.unfussysoftware.Sediment. If it isn’t installed, tell me and stop.

Set the server up the way this app sets up a local MCP server; if a step
is mine to take, tell me and wait. It starts Sediment itself when needed.

You’ll see its tools in a new conversation. Then call tags: a reply means
the connection works. Tell me in one sentence that Sediment is connected
and how many tags my shelf has; if tags fails, tell me what it said.

The server’s own instructions say how to file a page.
```

### In Claude Cowork

A Claude Cowork agent runs in the cloud, not on your Mac, so it can’t set
the server up itself. Install the
[Sediment plugin](https://github.com/unfussy-software/sediment-plugin)
instead: download `sediment.plugin` from its latest release and upload it
under Customize ▸ Plugins.
