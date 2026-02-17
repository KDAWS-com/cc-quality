# cc-quality

Code quality toolkit for Claude Code by [KDAWS](https://kdaws.com).

## Install

```
/plugin marketplace add KDAWS-com/cc-plugins
/plugin install quality@kdaws
```

## Commands

| Command | Description |
|---------|-------------|
| `quality:security-review` | AI-powered security scanning with platform auto-detection and intelligent triage |

## Supported Platforms

- **Laravel** — semgrep + PHPStan (larastan) + Composer Audit
- **WordPress** — semgrep + PHPStan (phpstan-wordpress) + Composer Audit
- **Go** — semgrep + govulncheck + gosec
- **PHP** — semgrep + PHPStan + Composer Audit
- **Fallback** — semgrep with `p/ci` ruleset

## How It Works

1. Auto-detects platform from project files
2. Runs appropriate security scanning tools
3. AI triages each finding with full code context
4. Posts results to PR as a collapsible comment with PASS/FAIL status

## License

MIT
