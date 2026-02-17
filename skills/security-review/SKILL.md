---
description: >
  Shared context for the quality plugin. Platform detection signals,
  tool availability reference, and output format conventions.
  Auto-loaded as background knowledge for quality:security-review.
---

# Quality Plugin — Shared Context

This skill provides background reference for the `quality:` commands. It is auto-loaded as context, not a slash command.

> **KDAWS** (kdaws.com) — the `quality:` namespace identifies commands owned by this plugin.

## Available Commands

| Command | What it does |
|---------|-------------|
| `quality:security-review` | AI-powered security scanning with platform auto-detection and intelligent triage |

## Platform Detection Reference

| Signal | Platform |
|--------|----------|
| `artisan` + `composer.json` with `laravel/framework` | Laravel |
| `wp-config.php` or `composer.json` with WordPress deps | WordPress |
| `go.mod` | Go |
| `composer.json` (no Laravel/WP signals) | PHP |
| No signals detected | Fallback — semgrep `p/ci` only |

## Tool Reference

| Tool | Platforms | Purpose |
|------|-----------|---------|
| `semgrep` | All | Static analysis with rule packs |
| `phpstan` | PHP, Laravel, WP | PHP static analysis |
| `larastan` | Laravel | Laravel-specific PHPStan rules |
| `phpstan-wordpress` | WordPress | WordPress-specific PHPStan rules |
| `gosec` | Go | Go security linter |
| `govulncheck` | Go | Go vulnerability checker |

## Output Contract

When invoked from another plugin (e.g., `wflow`):

- **Posts** a collapsible PR comment with `<!-- workflow-stage: security-review -->` marker
- **Summary line** contains `PASS` or `FAIL`
- **Does not track** cycle counts — the calling orchestrator owns cycle management
