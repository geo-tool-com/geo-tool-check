# Changelog

All notable changes to this project are documented here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versions follow
[Semantic Versioning](https://semver.org/).

## [1.1.0] - 2026-10-02

### Added

- 13 new checks (37 in total, same score as geo-tool.com): snippet permission
  (`nosnippet`, `max-snippet:0`, also via `X-Robots-Tag`), `Crawl-delay` and
  declared sitemap in robots.txt, `html lang`, Open Graph link preview,
  question-form headings, heading order, `main`/`article` landmark, JSON-LD
  validity, Organization/Person with `sameAs`, WebSite node on the homepage,
  article author as a Person, and links to legal notice/contact/about.
- llms.txt is checked for substance (at least five lines and one link).
- Crawler catalogue: Claude-SearchBot, Claude-User, Perplexity-User,
  DuckAssistBot.
- `check_citability` scores pasted text as a fragment and no longer expects
  page-level signals from it.

- Strict TypeScript, ESLint, Prettier, and a vitest suite with a local-only
  fixture server and network guard (no third-party calls in tests).
- Golden-master tests that freeze CLI output and exit codes byte-for-byte.
- `npm run verify:package`: packs the tarball, installs it in isolation, runs
  both executables, initializes the MCP server, and checks for dependency and
  cost-leak regressions.
- GitHub Actions CI (Node 18 and 22), Dependabot, issue forms, PR template,
  contributing/security/conduct policies, and English documentation in `docs/`.

### Changed

- Internal refactor only: CLI parsing/rendering and MCP protocol handling are
  now pure, tested modules; behavior, output bytes, and exit codes are frozen
  by the golden master. The MCP server now reports the package version.

## [1.0.1] - 2026-08-25

### Added

- `mcpName` for the Official MCP Registry; repository moved to geo-tool-com.

## [1.0.0] - 2026-08-24

### Added

- Initial release: `geo-tool-check` CLI and MCP server (three tools:
  `check_ai_readiness`, `check_ai_crawlers`, `check_citability`).
