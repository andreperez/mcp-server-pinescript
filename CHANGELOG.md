# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.4.1] - 2026-03-02

### Added
- **parameter-naming-validator.ts** — Added missing Pine Script v6 `singleWord` parameters present
  in the language before the original repository was published (Aug 2025) but absent from the Sets:
  `bordercolor`, `wickcolor` (`plotcandle()`; since Oct 2019), `fillgaps` (`fill()`; since Mar 2021),
  `timezone` (`time()` / `time_close()`; since Jul 2021), `extend` (`line.new()`), `text`
  (`label.new()` / `box.new()` content), `textalign` (`label.new()` horizontal alignment — distinct
  from `text_halign` which is for tables/boxes), `anchor` (`ta.vwap()`; since Jun 2022),
  `immediately` (`strategy.close()` / `strategy.close_all()`; since Jun 2022), `developing`
  (`ta.pivot_point_levels()`; since Aug 2022), `backadjustment` (`ticker.new()` /
  `ticker.modify()`; since Aug 2024).
- **parameter-naming-validator.ts** — Added missing Pine Script v6 `snakeCase` parameters:
  `stdev_mult` (`ta.vwap()`; since Jun 2022), `comment_profit`, `comment_loss`,
  `comment_trailing`, `alert_profit`, `alert_loss`, `alert_trailing` (`strategy.exit()`; since
  Jun 2022), `trail_price`, `trail_points`, `trail_offset` (`strategy.exit()`),
  `explicit_plot_zorder` (`indicator()` / `strategy()`; since Jul 2021),
  `fill_price` (`strategy.default_entry_qty()`; since Sep 2023).

### Notes
- `resolution_gaps` was **intentionally excluded**: it was a parameter of `study()`, which was
  removed in Pine Script v5 (replaced by `indicator()`). The parameter does not exist in any
  Pine Script v6 function.

## [3.4.0] - 2026-03-02

### Fixed
- **validator.js** — `INVALID_LINE_CONTINUATION` false positive on switch arm lines: the `>` in
  the `=>` operator incorrectly matched the comparison operator regex pattern. Lines containing `=>`
  are now skipped before operator checks.
- **validator.js** — `INVALID_LINE_CONTINUATION` false positive for multi-line expressions inside
  parentheses. Pine Script v6 (December 2025 release) explicitly allows any indentation for wrapped
  lines enclosed in parentheses. Added parenthesis-depth tracking across lines; operator checks are
  skipped when `entryParenDepth > 0`.
- **parameter-naming-validator.ts** — `parameter_validation` false positive for single-character
  parameter names `x`, `y`, `a`, `b`, `c`, `n`, `i`, `j`, `k`. These are legitimately used in
  Pine Script built-in drawing and math functions. Added `VALID_SINGLE_CHAR_PARAMS` allowlist.
- **index.ts** — `naming_convention` false positive for `UPPER_SNAKE_CASE` identifiers (e.g.,
  constant names like `GRP_SR1`, color constants). Pine Script convention allows `UPPER_SNAKE_CASE`
  for constants. Updated `checkNamingConvention()` to also allow `snake_case` variable names.
- **index.ts** — `plot_title` false positive when `title =` is written with a space before `=`.
  Updated `checkPlotTitle()` regex to `\btitle\s*=` to match both forms.

### Added
- **parameter-naming-validator.ts** — Added missing Pine Script v6 parameters to `singleWord` Set:
  `x`, `y`, `x1`, `y1`, `x2`, `y2`, `n`, `linestyle` (Sep 2025), `timeframe`, `gaps`,
  `lookahead`, `currency`, `dividends`, `splits`, `earnings`, `ignore_dividends_adjustments`.
- **parameter-naming-validator.ts** — Added missing Pine Script v6 parameters to `snakeCase` Set:
  `calc_bars_count` (May 2024), `behind_chart` (Oct 2024), `settlement_as_close` (Aug 2024),
  `timeframe_bars_back` (Oct 2025), `disable_alert`, `ignore_invalid_symbol`,
  `ignore_invalid_timeframe`, `qty_percent`, `bars_back`, and common `strategy.*` parameters.

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.21] - 2025-09-16

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.20] - 2025-09-16

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.19] - 2025-09-16

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.18] - 2025-09-13

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.17] - 2025-09-12

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.16] - 2025-09-12

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.15] - 2025-09-11

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.14] - 2025-09-11

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.13] - 2025-09-11

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.12] - 2025-09-11

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.11] - 2025-09-10

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.10] - 2025-09-09

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.9] - 2025-09-09

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.8] - 2025-09-08

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.7] - 2025-09-08

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.6] - 2025-09-07

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.5] - 2025-09-07

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.4] - 2025-09-07

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.3] - 2025-08-25

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.2] - 2025-08-22

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.1] - 2025-08-19

### Fixed
- Automated patch version bump with validation enhancements

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [3.3.0] - 2025-08-19

### Added
- Implement enterprise-grade automation with git hooks and validation enhancements
- Add comprehensive git hooks automation system (.githooks/ directory)
- Implement pre-commit validation: build, test, lint, version bump, changelog
- Add post-commit automatic git tagging
- Create session type management system for semantic versioning
- Add CHANGELOG.md automation to prevent sync issues
- Clean up unused JavaScript automation scripts (1,348 lines removed)
- Enhance Pine Script validation with new comprehensive rules
- Update documentation with git hooks setup and workflow
- Maintain backward compatibility for all MCP interfaces

🤖 Generated with automated version management

Co-Authored-By: Claude <noreply@anthropic.com>

---

## [2.0.0] - 2025-07-28

### ⚠️ BREAKING CHANGES
- **File Structure**: Replaced `functions.json` and `language.json` with single `language-reference.json`
- **Data Format**: MCP server now loads consolidated language reference instead of separate files
- **API Changes**: Internal preloading mechanism restructured to use unified data structure

### Added
- **Complete Pine Script Coverage**: 457 functions + 427 variables/constants/keywords/types/operators/annotations
- **Manual HTML Parser**: Custom parser for Pine Script® language reference manual bypassing Firecrawl limitations
- **Semantic Categorization**: Proper categorization of language elements with metadata
- **Enhanced Statistics**: Detailed breakdown of language element categories in server startup
- **Consolidated Scripts**: New `create-language-reference.js` and enhanced `parse-html-reference.js`

### Fixed
- **Parameter Naming**: Confirmed correct snake_case naming (`text_color`, `default_qty_type`)
- **Function Signatures**: 100% accurate function signatures from official language manual
- **JavaScript Rendering Issues**: Manual HTML parsing eliminates Firecrawl JavaScript dependency problems
- **Documentation Quality**: Eliminated 404 errors and incomplete function data

### Changed
- **Memory Usage**: Improved efficiency with single file loading (15MB total)
- **Performance**: Faster server startup and response times
- **File Organization**: Cleaner structure with single authoritative reference file
- **Documentation**: Updated README, MAINTAINER, USER-GUIDE, and QUALITY-ANALYSIS to reflect new structure

### Removed
- `functions.json` (incomplete Firecrawl data)
- `language.json` (empty/error content)
- `functions-from-html.json` (consolidated)
- `variables-from-html.json` (consolidated)

### Migration Guide
For users upgrading from v1.x:
1. The MCP server will automatically use the new `language-reference.json` file
2. No client-side changes required - the MCP protocol interface remains the same
3. Verify `docs/processed/` contains: `index.json`, `language-reference.json`, `style-rules.json`

---

## [1.3.0] - 2025-07-27

### Added
- Enhanced documentation quality validation
- Systematic fixes for Firecrawl scraping issues
- Manual HTML parsing capability for JavaScript-dependent pages

### Fixed
- Removed invalid URLs from scraping configuration
- Added quality validation to detect error pages
- Enhanced processing to skip invalid content

---

## [1.2.0] - Previous Release
### Added
- Pine Script function signature extraction
- Parameter name validation for table.cell function

---

## [1.1.2] - Previous Release
### Fixed
- Updated documentation with correct CLI usage

---

## [1.1.1] - Previous Release  
### Fixed
- npm install from GitHub repository

---

## [1.1.0] - Previous Release
### Added
- Enhanced documentation with CLI integration examples

---

## [1.0.0] - Initial Release
### Added
- Initial implementation of PineScript MCP Documentation Server