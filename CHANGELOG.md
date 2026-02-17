# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] - 2026-02-17

### Fixed
- Slash command now discoverable: created `commands/quality/security-review.md` with explicit `name: quality:security-review` frontmatter
- Follows Claude Code's one-file-per-command convention

### Changed
- `skills/security-review/SKILL.md` slimmed to shared context only (platform detection reference, tool table, output contract)
- Full command procedure moved to `commands/quality/security-review.md`

## [1.0.0] - 2026-02-17

### Added
- Initial plugin release as `quality`
- `quality:security-review` — AI-powered security scanning with platform auto-detection
- Platform detection for Laravel, WordPress, Go, PHP
- Semgrep, PHPStan, Composer Audit, govulncheck, gosec integration
- AI-powered triage with blocking/dismissed/warning classification
- PR comment posting with audit trail
- Output contract for cross-plugin invocation
