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

- **Real Problems, Real Solutions** - Built from actual needs, not theoretical use cases
- **Cross-Platform** - Same commands work on Windows, Linux, and macOS
- **Composable** - Tools work together but don't require each other
- **No Bloat** - Each tool does one thing well
- **Transparent Behavior** - You control what happens, tools don't guess

---

## Who Should Use DazzleTools?

### 🏠 Home Users
- Fix Windows "No Internet, Secured" false positives
- Back up photos/videos with verification they copied correctly
- Organize large file collections
- See what programs are using your network ports
- Manage startup programs to speed up your computer

### 💼 IT Professionals
- Automate file verification workflows
- Audit and manage Windows services
- Create reproducible system configurations
- Monitor process changes and resource usage
- Standardize file operations across mixed environments

### 👨‍💻 Developers
- Integrate file operations into build systems
- Manage git repositories with batch operations
- Verify deployment file integrity
- Automate testing workflows
- Debug network connectivity issues

### 🎨 Content Creators
- Organize and verify media file archives
- Manage large asset libraries across drives
- Clean up temporary files safely
- Monitor system resources during rendering
- Preserve project files with confidence

---

## Featured Tools

### 🌟 Top 5 Most Popular

#### 1. [NCSI Resolver](https://github.com/djdarcy/Windows-No-Internet-Secured-BUGFIX)
**Fix Windows "No Internet, Secured" false detection**

**License**: Proprietary (Free for personal use)

If Windows shows "No Internet, Secured" when you actually have internet, this tool fixes it. Runs silently as a Windows service and makes OneNote, OneDrive, and other Microsoft UWP apps work again.

```bash
# Install and run as Windows service
ncsi-resolver install
ncsi-resolver start
```

**Features**:
- One-click solution to Windows connectivity detection bug
- Runs as Windows service (starts automatically)
- Works silently in background
- No ongoing configuration needed
- Fixes Microsoft Store apps, OneDrive sync, OneNote, etc.

**Use Cases**:
- Corporate networks with captive portals
- VPN environments where NCSI probes fail
- Networks that block Microsoft connectivity checks
- Systems where UWP apps won't connect despite having internet

---

#### 2. [process-delta](https://github.com/djdarcy/process-delta)
**Process and service snapshot and management tool**

**License**: GPL 3.0

Track what's running on your system, compare snapshots, and automate startup optimizations. Perfect for gaming setups, system diagnostics, and understanding what's consuming resources.

```bash
# Take a snapshot of running processes
process-delta snapshot before.json

# Start your game or application
# ...

# Compare to see what changed
process-delta compare before.json after.json

# Automate stopping unnecessary services for gaming
process-delta apply gaming-profile.json
```

**Features**:
- Snapshot running processes and services
- Compare snapshots to see what changed
- Export/import service configurations
- Automate service start/stop operations
- Cross-platform (Windows, Linux, macOS)

**Use Cases**:
- Gaming optimization (stop unnecessary services before gaming)
- Malware detection (compare process lists)
- System diagnostics (what's running and why?)
- Performance optimization (identify resource hogs)
- Automation (reproducible system states)

---

#### 3. [preserve](https://github.com/DazzleTools/preserve)
**File preservation with verification and restoration**

**License**: GPL 3.0
**PyPI**: `pip install dazzle-preserve`

Copy files with confidence. Every file is verified with checksums, and you get detailed reports showing what succeeded and what failed. Multiple backup strategies (flat, relative, absolute) for different needs.

```bash
# Copy with verification (family photos example)
preserve COPY --src "C:\Users\You\Pictures" --dst "E:\Backup\Pictures" --rel --recursive

# Verify existing backup
preserve VERIFY --src "C:\Users\You\Pictures" --dst "E:\Backup\Pictures" --rel

# Restore from backup
preserve RESTORE --src "E:\Backup\Pictures" --dst "C:\Users\You\Pictures" --rel
```

**Features**:
- Hash-based verification (MD5, SHA1, SHA256, SHA512)
- Multiple backup strategies (flat, relative, absolute paths)
- Detailed reports (CSV, JSON, text)
- Restore capability with verification
- Metadata preservation (timestamps, permissions)
- Cross-platform path handling

**Use Cases**:
- Family photo/video backups with verification
- Project file preservation before major changes
- Archive verification (ensure files haven't corrupted)
- Migration between drives/systems
- Compliance (provable file integrity)

---

#### 4. [listall](https://github.com/djdarcy/listall)
**Recursive directory listing and analysis**

**License**: GPL 3.0

Generate detailed directory trees with file sizes, counts, and structure. Perfect for documentation, disk usage analysis, and understanding large directory hierarchies.

```bash
# Generate directory tree
listall /path/to/directory

# Export to file
listall /path/to/directory > directory-structure.txt

# Include file sizes
listall --sizes /path/to/directory
```

**Features**:
- Recursive directory traversal
- File size reporting
- File count statistics
- Tree visualization
- Export to multiple formats
- Cross-platform compatibility

**Use Cases**:
- Disk usage analysis (what's taking up space?)
- Project documentation (directory structure)
- Archive cataloging
- Before/after comparisons
- File organization planning

---

#### 5. [open-ports-and-programs](https://github.com/djdarcy/open-ports-and-programs)
**Network port and program diagnostics**

**License**: GPL 3.0

See what programs are listening on network ports. Essential for debugging connectivity issues, finding port conflicts, and understanding what's talking to the internet.

```bash
# Show all listening ports and programs
open-ports-and-programs

# Find what's using a specific port
open-ports-and-programs --port 8080

# Export report
open-ports-and-programs --output report.txt
```

**Features**:
- List all listening ports
- Identify programs using each port
- Find port conflicts
- Export reports
- Cross-platform (Windows, Linux, macOS)
- No admin rights required (for most operations)

**Use Cases**:
- Debugging "port already in use" errors
- Security auditing (what's listening?)
- Development (find that forgotten test server)
- Network troubleshooting
- Firewall configuration planning

---

## Additional Tools

### File Operations

#### [dazzlelink](https://github.com/DazzleTools/dazzlelink)
Enhanced file reference and linking system. Create intelligent file links with metadata tracking.

**License**: GPL 3.0

```bash
# Create enhanced file link
dazzlelink create /source/file.txt --dst /destination/
```

#### [dazzlesum](https://github.com/DazzleTools/dazzlesum)
Advanced checksum verification and management. Calculate, store, and verify file hashes at scale.

**License**: GPL 3.0

```bash
# Calculate checksums for directory
dazzlesum calculate /path/to/files --algorithm sha256

# Verify against stored checksums
dazzlesum verify /path/to/files
```

#### [pattern-break](https://github.com/DazzleTools/pattern-break)
Pattern matching and text transformation. Find and replace with regex, template processing, bulk file operations.

**License**: GPL 3.0

```bash
# Rename files by pattern
pattern-break rename --pattern "photo_*.jpg" --template "vacation_{date}_{count}.jpg"
```

#### [folder-datetime-fix](https://github.com/djdarcy/folder-datetime-fix)
Correct folder modification times based on contents. Useful after copying folders (which resets timestamps).

**License**: GPL 3.0

```bash
# Fix folder timestamps to match newest file inside
folder-datetime-fix /path/to/folders
```

#### [temp-renamer](https://github.com/djdarcy/temp-renamer)
Safely rename files using temporary names. Prevents accidental overwrites and handles case-sensitivity issues.

**License**: GPL 3.0

```bash
# Rename with temporary staging
temp-renamer --src "Photo.JPG" --dst "photo.jpg"
```

---

### Git Operations

#### [git-repokit](https://github.com/djdarcy/git-repokit)
Batch operations across multiple git repositories. Find, clone, pull, and manage collections of repos.

**License**: GPL 3.0

```bash
# Update all repositories in directory
git-repokit pull-all /path/to/repos

# Find all git repos
git-repokit find /path/to/search
```

---

### System Management

#### [discord-cleanup](https://github.com/djdarcy/discord-cleanup)
Clean up Discord cache and temporary files. Free up disk space from accumulated Discord data.

**License**: GPL 3.0

```bash
# Clean Discord cache
discord-cleanup --cache

# Full cleanup (cache + logs)
discord-cleanup --full
```

---

## Installation

### Individual Tools

Most tools will be available via PyPI:

```bash
# Install individual tools
pip install dazzle-preserve
pip install dazzle-dazzlelink
pip install dazzle-dazzlesum
# ... more tools coming to PyPI soon
```

### Development Installation

```bash
# Clone and install in development mode
git clone https://github.com/DazzleTools/<tool-name>
cd <tool-name>
pip install -e .
```

### Build Environment *(Coming Soon)*

The Dazzle build environment will provide one-command setup:

```bash
# Future: Install all tools at once
setenv.py install --tools all
```

---

## Tool Categories

### By Function

| Category | Tools |
|----------|-------|
| **File Operations** | preserve, dazzlelink, dazzlesum, listall, folder-datetime-fix, temp-renamer |
| **System Diagnostics** | open-ports-and-programs, process-delta |
| **Network/Connectivity** | NCSI Resolver |
| **Git Workflows** | git-repokit |
| **Text Processing** | pattern-break |
| **Cleanup** | discord-cleanup |

### By Audience

| Audience | Recommended Tools |
|----------|-------------------|
| **Home Users** | NCSI Resolver, preserve, listall |
| **IT Professionals** | process-delta, open-ports-and-programs, preserve, dazzlesum |
| **Developers** | git-repokit, dazzlelink, pattern-break, temp-renamer |
| **Content Creators** | preserve, listall, folder-datetime-fix |

---

## Common Workflows

### 1. System Gaming Optimization

```bash
# Take snapshot before optimization
process-delta snapshot baseline.json

# Create gaming profile (stop unnecessary services)
process-delta create-profile gaming.json --stop-nonessential

# Apply before gaming
process-delta apply gaming.json

# Restore after gaming
process-delta restore baseline.json
```

### 2. Photo Backup with Verification

```bash
# Initial backup
preserve COPY --src "%USERPROFILE%\Pictures" --dst "E:\Backup\Pictures" --rel --recursive

# Verify backup succeeded
preserve VERIFY --src "%USERPROFILE%\Pictures" --dst "E:\Backup\Pictures" --rel

# Monthly verification
preserve VERIFY --src "E:\Backup\Pictures" --dst "%USERPROFILE%\Pictures" --rel
```

### 3. Project File Preservation

```bash
# Before major refactoring
preserve COPY --src "./my-project" --dst "./backups/my-project-2025-11-07" --rel --recursive

# Work on changes...

# If something breaks, restore
preserve RESTORE --src "./backups/my-project-2025-11-07" --dst "./my-project" --rel
```

### 4. Network Debugging

```bash
# See what's listening
open-ports-and-programs

# Check specific port
open-ports-and-programs --port 3000

# Export for documentation
open-ports-and-programs --output network-audit.txt
```

### 5. Multi-Repository Management

```bash
# Find all git repos in code directory
git-repokit find ~/code > repos.txt

# Update all at once
git-repokit pull-all ~/code

# Check status across all repos
git-repokit status-all ~/code
```

---

## Tool Development Guidelines

### Design Principles

1. **Single Responsibility** - Each tool does one thing well
2. **Composability** - Tools can be combined in workflows
3. **Cross-Platform** - Same behavior on Windows, Linux, macOS
4. **Explicit Control** - User controls behavior, no hidden magic
5. **Robust Error Handling** - Clear error messages, graceful failures

### Licensing Strategy

- **Core tools**: GPL 3.0 (keeps tools open and freely available)
- **Some specialized tools**: Proprietary with commercial licenses
  - Clearly marked in project READMEs
  - Free for personal use in many cases
  - Developed as commercial products to fund ecosystem

### Quality Standards

- **Cross-platform testing** on Windows, Linux, macOS
- **Error handling** for common failure modes
- **Documentation** with examples and use cases
- **Version compatibility** with semantic versioning
- **Dependencies** kept minimal

---

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

---

## Platform Support

| Tool | Windows | Linux | macOS |
|------|---------|-------|-------|
| NCSI Resolver | ✅ Full | ❌ N/A | ❌ N/A |
| process-delta | ✅ Full | ✅ Full | ✅ Full |
| preserve | ✅ Full | ✅ Full | ✅ Full |
| listall | ✅ Full | ✅ Full | ✅ Full |
| open-ports-and-programs | ✅ Full | ✅ Full | ✅ Full |
| dazzlelink | ✅ Full | ✅ Full | ✅ Full |
| dazzlesum | ✅ Full | ✅ Full | ✅ Full |
| pattern-break | ✅ Full | ✅ Full | ✅ Full |
| git-repokit | ✅ Full | ✅ Full | ✅ Full |
| folder-datetime-fix | ✅ Full | ✅ Full | ✅ Full |
| temp-renamer | ✅ Full | ✅ Full | ✅ Full |
| discord-cleanup | ✅ Full | ✅ Full | ✅ Full |

**Notes**:
- NCSI Resolver is Windows-specific (solves Windows-specific problem)
- All other tools work consistently across platforms
- Python 3.8+ required for all tools

---

## Migration Status

**Current State**: DazzleTools organization is being established. Many tools currently live in personal repositories and will be migrated selectively.

### Available Now

- **preserve**: Published on PyPI as `dazzle-preserve`
- **NCSI Resolver**: Available at [Windows-No-Internet-Secured-BUGFIX](https://github.com/djdarcy/Windows-No-Internet-Secured-BUGFIX)
- Most other tools available in personal repositories

### Coming Soon

- Migration of remaining tools to DazzleTools organization
- PyPI packages for all tools with `dazzle-` prefix
- Integrated installation via build environment
- Comprehensive documentation and tutorials

---

## Contributing

Contributions are welcome! Each tool has its own repository and contribution guidelines.

### General Process

1. Fork the tool repository
2. Create a feature branch
3. Make your changes with clear commit messages
4. Add tests for new functionality
5. Ensure cross-platform compatibility
6. Submit a pull request

### Development Setup

```bash
# Clone tool repository
git clone https://github.com/DazzleTools/<tool-name>
cd <tool-name>

# Install in development mode
pip install -e ".[dev]"

# Run tests
pytest tests/ -v

# Test cross-platform (if possible)
# ... test on Windows, Linux, macOS
```

### Code Quality Standards

- **Cross-platform**: Test on multiple operating systems
- **Type hints**: Use type annotations for clarity
- **Docstrings**: Document all public functions
- **Tests**: Coverage for key functionality
- **Formatting**: Follow PEP 8

---

## 💰 Sustainability

**DazzleTools** is part of the [DazzleProj](https://github.com/DazzleProj) ecosystem.

**Current sponsorship: $0/month | Goal: $1,000/month**

### Why Sponsor?

If you're using DazzleTools professionally or personally:

- **Time saved**: Most users save 5-10 hours/month
- **Alternative cost**: Building these yourself would cost $10,000+
- **Commercial alternatives**: Often $50-200/month each
- **Supporting**: $25-100/month helps ensure continued development

**Real value calculation** for IT professional:
- Time saved: ~8 hours/month
- Your rate: $75/hour
- Value received: **$600/month**
- Contributing: $50/month is fair exchange

### How to Help

1. 💵 **[Sponsor on GitHub](https://github.com/sponsors/djdarcy)** - Direct support
2. ⭐ **Star repositories** - Increases visibility
3. 💬 **Share with colleagues** - Help others discover useful tools
4. 📝 **Write about your experience** - Blog posts, tutorials
5. 🔧 **Contribute code** - Make tools even better

### Sponsor Benefits

- 🌟 **$5/month** - Supporter: Name in README
- 🌟🌟 **$25/month** - Contributor: Logo on DazzleProj.com
- 🌟🌟🌟 **$100/month** - Bronze Sponsor: Priority issue handling
- 🌟🌟🌟🌟 **$500/month** - Silver Sponsor: 1 hour consulting/month
- 🌟🌟🌟🌟🌟 **$2,000/month** - Gold Sponsor: 5 hours consulting/month + priority features

---

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
- **[DazzleAI](https://github.com/DazzleAI)** - AI development tools

### Related Ecosystems

- **[TodoAI](https://github.com/Todo-AI)** - Task-based OS with AI integration
- **[ZeroMeld](https://github.com/ZeroMeld)** - Open-source CRM for public discussion boards

---

## Roadmap

### Near Term (Q4 2025 - Q1 2026)

- ✅ Establish DazzleTools organization
- 🚧 Migrate tools from personal repositories
- 🚧 Publish remaining tools to PyPI with `dazzle-` prefix
- 🚧 Create comprehensive documentation
- 🚧 Set up GitHub Sponsors

### Medium Term (Q2-Q3 2026)

- Cross-platform build environment integration
- Training materials and video tutorials
- Community-contributed tools
- Enhanced documentation with more examples
- Tool integration workflows

### Long Term (2026+)

- Training programs for system administrators
- Enterprise support options
- Hosted tool execution environments
- Additional commercial tools (to fund development)
- Expanded platform support

*Roadmap depends on community support and sponsorship.*

---

## License

DazzleTools uses a hybrid licensing approach:

- **Most tools**: GPL 3.0 (keeps tools open and freely available)
- **Some tools**: Proprietary licenses with free personal use
  - Clearly marked in individual project repositories
  - Commercial licensing available

See individual tool repositories for specific licensing information.

---

## Contact

- **GitHub**: [@djdarcy](https://github.com/djdarcy)
- **Issues**: Use repository-specific issue trackers
- **Discussions**: [GitHub Discussions](https://github.com/DazzleTools/discussions)
- **Sponsorship**: [GitHub Sponsors](https://github.com/sponsors/djdarcy)
- **Website**: [DazzleProj.com](https://dazzleproj.com) *(coming soon)*

---

**Built by someone who got tired of reinventing the wheel** 🛠️

*Tools that solve real problems, work reliably, and respect your time.*
