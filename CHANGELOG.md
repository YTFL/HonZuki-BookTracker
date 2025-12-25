# Changelog

All notable changes to HonZuki will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.4.0] - 2025-12-25
### ✨ Added
- **Wishlist Sharing** - Users can now make their wishlist public and share it via a unique link. The link is generated with a default name of "<User>'s Wishlist".


### 🔧 Improved
- **Natural Sort** - Improved sorting logic for titles and authors to correctly handle numbers (e.g., "Vol 2" sorts before "Vol 10").


### 🐛 Fixed
- **Series Duplication** - Fixed an issue where assigning a book to an existing series would sometimes create a duplicate series entry instead of linking to the existing one.
- **Share Counts** - Fixed an issue where share book counts would display as 0 or be inaccurate due to race conditions or missing data fields.



### ⚠️ Known Issues / Current Status
- 🔴 **Authentication Disabled** - All users must use Guest Mode
- ❌ **No Cloud Sync** - Data stored locally only (in browser localStorage)
- ❌ **No Sharing Features** - Public share links disabled
- ✅ **All Core Features Work** - Full functionality in Guest Mode
- 📋 **Export Regularly** - Back up your library via Settings → Export
- 🔜 **Authentication Fix Planned** - Expected in future release

---

For detailed information about each release, see the [Releases](../../releases) page.
