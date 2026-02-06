# Changelog

All notable changes to HonZuki will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.13.0] - 2026-02-06
### ✨ Added
- **Series Selection Refactor** - Replaced text inputs with a searchable `SeriesCombobox` in Add Book, Edit Book, and Edit Wishlist forms.
- **Manual Series Creation** - Added explicit "Create New Series" workflow, preventing accidental creation of series via typos.
- **Search Enhancements** - Now displays **Wishlist Items** and **Shared Lists** in the search results, making it easier to find everything in one place.

### 🐛 Fixed
- **Stats Page** - Fixed corruption in "Total Pages Owned" statistic.
- **Sidebar Background** - Fixed sidebar on mobile not adapting to dynamic book page background colors.
- **Move to Library** - Fixed bug where moving a book from wishlist to library failed or created false entries.
- **Legacy Wishlist Items** - Fixed defensive parsing for legacy wishlist items during move operation.
- **Page Counts** - Enforced integer validation for page counts to prevent data corruption.
- **Wishlist Permissions** - Fixed permissions error when adding to wishlist.
- **Add Book Placeholder** - Fixed placeholder text styling (opacity/color) on Add Book page.
- **Reading Progress Input** - Fixed '0' persisting in page count input and removed spin buttons for cleaner UI.
- **Page Refresh 404** - Fixed race condition where refreshing book (or wishlist item) details page caused a 404 error.
- **Book Not Found UI** - Replaced generic 404 redirect with a helpful "Book Not Found" message and navigation options for both Library and Wishlist.
- **Wishlist Authors** - Fixed multiple authors input being treated as a single author string in Wishlist items; now correctly parses comma-separated names.
- **Reading Status Dates** - Fixed validation to prevent completed/dropped dates from being set before the start date; dates must now be on the same day or after the start date.
- **Reading Speed Loading** - Implemented localStorage caching to eliminate delayed loading of reading speed setting on Settings page; now loads instantly with the rest of the page.
- **Format Statistics** - Fixed inconsistency where books with null/empty formats were counted as "other" in stats but treated as "paperback" when filtering; library filtering now uses the same normalization logic as stats for accurate counts.
- **Sorting Preferences** - Fixed sorting preferences not persisting across page refreshes and browser sessions; preferences now saved to localStorage for both Library and Wishlist pages.


### ⚠️ Known Issues / Current Status
- 🔴 **Authentication Disabled** - All users must use Guest Mode
- ❌ **No Cloud Sync** - Data stored locally only (in browser localStorage)
- ✅ **Sharing Features** - Public share links enabled for authenticated users
- ✅ **All Core Features Work** - Full functionality in Guest Mode
- 📋 **Export Regularly** - Back up your library via Settings → Export
- 🔜 **Authentication Fix Planned** - Expected in future release
