# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

**fastlane-plugin-rename_android_package** is Cove's fork of the `fastlane-plugin-rename_android_package` fastlane plugin (renames the Android package). It is consumed by **cove-buildings-mobile** (android) via a git reference in that repo's `android/fastlane/Pluginfile`.

## Dependency Version Pinning

Dependencies are declared in `fastlane-plugin-rename_android_package.gemspec` (the `Gemfile` only loads it via `gemspec`). Per COMP-421:

- **Development dependencies are pinned to exact versions** (`spec.add_development_dependency('x', '= 1.2.3')`) so contributor builds are reproducible.
- **The `fastlane` runtime dependency is intentionally left as a range** (`>= 2.102.0`). Pinning it exact would over-constrain consumers — cove-buildings-mobile/android resolves `fastlane` from a git ref (currently 2.229.0), which must satisfy this plugin's requirement, so an exact pin here would break that build.
- **`bundler` is left unpinned** (it is the package manager, not a project dependency).
- `Gemfile.lock` is **gitignored** by library convention; reproducibility is enforced by the consumer's lockfile, not this repo's.

## Git Workflow

### Branch Naming Convention
Use the format: `<initials>/<type>/CAN-XXXXX-description`

**Types:** `chore`, `feature`, `fix`

**Examples:**
- `js/feature/CAN-12345-add-watch-list` - Feature with JIRA ticket
- `js/fix/CAN-12346-fix-login-bug` - Bug fix with JIRA ticket
- `js/chore/update-dependencies` - Chore without JIRA ticket
