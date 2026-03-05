# Changelog

All notable changes to this project will be documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-03-05

### Added
- Plugin manifest (`.claude-plugin/plugin.json`) for compatibility with the Claude Code plugin system
- `.gitignore` to prevent local settings files from being committed

### Changed
- Restructured from standalone configuration to a proper Claude Code plugin
- Moved skill from `.claude/skills/mermaid/` to `skills/generate/` at the plugin root
- Skill is now invoked as `/mermaid:generate` instead of `/mermaid`
- Updated GitHub Actions workflow to write to the new `skills/generate/references/` path
- Updated README with plugin-based installation instructions

### Removed
- `.claude/settings.local.json` (was untracked; now explicitly gitignored)
