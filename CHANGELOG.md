# Changelog

All notable changes to HonZuki will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.11.0] - 2025-12-27
### ✨ Added
- **Filtered Sharing** - Create shares based on dynamic criteria (Status, Shelves, Authors, Genres, Year).
- **Custom Share Workflow** - New "Select Books" step with search and checkboxes for Custom Shares.

### 🎨 Redesigned
- **Share Details UI** - Improved "Share" and "View Public" buttons with standard icons and native behavior.
- **Improved Interaction** - Clickable book rows in selection screens.

### � Fixed
- **Public Share Access** - Fixed links on public pages to point to correct public routes, preventing access errors.
- **Filtered Share Display** - Fixed public pages showing 0 books for filtered shares.
- **Permissions** - Updated rules to allow filtered shares.
- **Creation Errors** - Fixed undefined field errors during custom share creation.

### ⚠️ Known Issues / Current Status
- 🔴 **Authentication Disabled** - All users must use Guest Mode
- ❌ **No Cloud Sync** - Data stored locally only (in browser localStorage)
- ✅ **Sharing Features** - Public share links enabled for authenticated users
- ✅ **All Core Features Work** - Full functionality in Guest Mode
- 📋 **Export Regularly** - Back up your library via Settings → Export
- 🔜 **Authentication Fix Planned** - Expected in future release

---

For detailed information about each release, see the [Releases](../../releases) page.
