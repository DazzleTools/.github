# DazzleTools

**System Management Utilities for Everyone**

[![GitHub](https://img.shields.io/badge/GitHub-DazzleTools-blue?logo=github)](https://github.com/DazzleTools)
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

#### [NCSI Resolver](https://github.com/djdarcy/Windows-No-Internet-Secured-BUGFIX)
**Fix Windows "No Internet, Secured" false detection**

If Windows shows "No Internet, Secured" when you actually have internet, this tool fixes it. Runs silently as a Windows service and makes OneNote, OneDrive, and other Microsoft UWP apps work again.

```bash
# Install and run as Windows service
ncsi-resolver install
ncsi-resolver start
```

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
- **Discussions**: [GitHub Discussions](https://github.com/DazzleTools/discussions)
- **Sponsorship**: [GitHub Sponsors](https://github.com/sponsors/djdarcy)
- **Website**: [DazzleProj.com](https://dazzleproj.com) *(coming soon)*

