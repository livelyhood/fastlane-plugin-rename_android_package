# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

**fastlane-plugin-rename_android_package** is a Fastlane plugin (Ruby gem) for renaming Android packages in project files.

## Development Commands

```bash
# Install dependencies
bundle install

# Run tests and linting (default rake task)
bundle exec rake

# Run RSpec tests only
bundle exec rspec

# Run RuboCop linting only
bundle exec rubocop

# Auto-fix RuboCop issues
bundle exec rubocop -a
```

## Git Workflow

### Branch Naming Convention
Use the format: `<initials>/<type>/CAN-XXXXX-description`

**Types:** `chore`, `feature`, `fix`

**Examples:**
- `js/feature/CAN-12345-add-watch-list` - Feature with JIRA ticket
- `js/fix/CAN-12346-fix-login-bug` - Bug fix with JIRA ticket
- `js/chore/update-dependencies` - Chore without JIRA ticket
