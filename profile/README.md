# DazzleTools

**System Management Utilities for Everyone**

[![GitHub](https://img.shields.io/badge/GitHub-DazzleTools-blue?logo=github)](https://github.com/DazzleTools/.github)
[![License](https://img.shields.io/badge/License-GPL%203.0-green.svg)](LICENSE)
[![Sponsor](https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?logo=github-sponsors)](https://github.com/sponsors/djdarcy)

> Command-line utilities for file management, system diagnostics, process control, and everyday computing tasks. Works the same on Windows, Linux, and macOS.

---

## What is DazzleTools?

**DazzleTools** is a collection of standalone command-line utilities designed to solve real-world system management problems. From fixing Windows connectivity bugs to backing up your family photos with verification, these tools make everyday computing tasks easier and more reliable.

### Philosophy

- **Cross-Platform** - Same commands work on Windows, Linux, and macOS
- **Composable** - Tools work together but don't require each other
- **No Bloat** - Each tool does one thing well
- **Transparent Behavior** - You control what happens, tools don't guess

---

## Featured Tool

### [DazzleCMD (`dz`)](https://github.com/DazzleTools/dazzlecmd)
**Brew for your own tools — many tools, one command, any machine**

Install `dz` and every tool in DazzleTools is immediately at your fingertips — no cloning individual repos, no PATH configuration, no per-tool setup. DazzleCMD is the unified interface that brings the entire collection under one command:

```bash
pip install dazzle-dz

# The full DazzleTools collection, ready to use
dz list                        # See everything available
dz dos2unix myfile.txt         # Run any tool directly
dz info preserve               # Get details about a tool
```

But DazzleCMD isn't just for DazzleTools — it's a personal tool manager for any developer. Everyone has scripts scattered across machines that aren't version-controlled, break on different platforms, and can't be found when needed. `dz` solves this: turn any script into a versioned, namespaced tool available on any computer, any platform, without setting up a new git repo for each one.

```bash
# Create a tool from your script — immediately versioned and organized
dz new my-backup --full -d "Backup important files with verification"

# Import an entire GitHub org or user's repos as a kit
dz kit import --org djdarcy    # Every tool, namespaced and ready

# Your tools work the same everywhere
dz my-backup ~/documents /mnt/nas
dz rename-files *.txt --dry-run
```

**What makes it different from brew, just, or a ~/bin directory?**
- **Your tools, not just community packages** — `dz new` scaffolds, versions, and organizes scripts you already have
- **Import whole collections** — pull in a GitHub org or user's repos and have every tool instantly available
- **Polyglot dispatch** — Python, bash, PowerShell, compiled binaries — `dz` runs them all transparently
- **No PATH hell** — one command works across Windows, Linux, and macOS without per-machine setup
- **Namespace collision prevention** — `work:deploy` and `personal:deploy` coexist cleanly
- **Kit-based curation** — bundle tools into logical groups (DazzleTools itself is just one kit)
- **Tool lifecycle** — one-off scripts start in `dz`, grow into full repos with CI/CD and tests, then return to `dz` as submodules. The ecosystem captures the entire journey from quick hack to mature project — and tools never leave

## Dependencies

Most DazzleTools use [DazzleLib](https://github.com/DazzleLib) libraries:

```
DazzleLib (Foundation)
├── dazzle-filekit
├── dazzle-tree-lib
└── UNCtools
    ↓ (used by)
DazzleTools
├── preserve (uses dazzle-filekit)
├── dazzlelink (uses dazzle-filekit)
├── dazzlesum (uses dazzle-filekit)
├── listall (uses dazzle-tree-lib)
└── Other tools
```

See individual tool repositories for specific dependencies.

## Documentation

- **Tool-Specific Docs**: See individual repository READMEs
- **Tutorials**: [DazzleProj.com](https://dazzleproj.com) *(coming soon)*
- **Examples**: Check `examples/` directories in each tool
- **Discussions**: [GitHub Discussions](https://github.com/DazzleTools/discussions)

---

## Related Projects

### Part of DazzleProj Ecosystem

- **[DazzleProj](https://github.com/DazzleProj)** - Ecosystem coordination
- **[DazzleLib](https://github.com/DazzleLib)** - Foundation libraries
- **[DazzleTools](https://github.com/DazzleTools)** - Command-line tools ← *You are here*
- **[DazzleNodes](https://github.com/DazzleNodes)** - ComfyUI custom nodes
- **[DazzleML](https://github.com/DazzleML)** - AI development tools

### Related Ecosystems

- **[TodoAI](https://github.com/Todo-AI)** - Task-based OS with AI integration
- **[ZeroMeld](https://github.com/ZeroMeld)** - Open-source CRM for public discussion boards

---

## Roadmap

### Near Term (Q4 2025 - Q1 2026)

- 🚧 Migrate tools from personal repositories
- 🚧 Publish remaining tools to PyPI with `dazzle-` prefix

### Medium Term (Q2-Q3 2026)

- Cross-platform build environment integration
- Tool integration workflows

### Long Term (2026+)

- Hosted tool execution environments
- Additional commercial tools (to fund development)
- Expanded platform support

*Roadmap depends on community support and sponsorship.*

---

## Contact

- **GitHub**: [@djdarcy](https://github.com/djdarcy)
- **Issues**: Use repository-specific issue trackers
- **Discussions**: [GitHub Discussions](https://github.com/orgs/DazzleTools/discussions)
- **Sponsorship**: [GitHub Sponsors](https://github.com/sponsors/djdarcy)
- **Website**: [DazzleProj.com](https://dazzleproj.com) *(coming soon)*

