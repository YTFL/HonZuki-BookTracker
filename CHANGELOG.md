# Changelog

All notable changes to HonZuki will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---
## [2.14.0] - 2026-03-25
### ✨ Added
- **Publisher pages** - Dedicated publisher detail page (`/publishers/[name]`) with overview, responsive statistics, filters, and a books list with layout/sort controls.
- **Publishers index** - Main `/publishers` catalog with unique animations, gradient accents, and an in-page search to quickly find publishers.
- **Publisher combobox** - Searchable `PublisherCombobox` used in Add Book, Edit Book, and Edit Wishlist forms for consistent publisher selection (supports typed values).
- **Search routing** - Publisher results in global search now link to publisher detail pages.
- **Rename dialogs** - Batch rename dialogs for `Author` and `Publisher`, which update linked books and redirect to the new entity route.

### ♻️ Changed
- Modernized `Authors` and `Genres` detail pages to use the same shell/layout and responsive stats grid as publishers for visual consistency.
- Sidebar navigation: `Categories` converted to a dropdown (sub-menu) and now defaults expanded; `Stats` was restored directly under `Categories` in the menu order.
- Small UI moves: moved publisher rename control into the publisher header card, removed the old catalog percentage badge, and relabeled the top metric from "Read" to "Reading".

### 🐛 Fixed
- Fixed a hook-order bug in the publishers index that caused the runtime error "Rendered fewer hooks than expected" by ensuring hooks are called before any early return.

---

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

---

## [2.12.0] - 2026-01-09
### ✨ Added
- **Refetch Cover** - Added a button in the Edit Book page to update cover images from online sources (Google Books, Open Library) via ISBN or title/author.

---

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

---

## [1.4.0] - 2025-12-25
### ✨ Added
- **Wishlist Sharing** - Users can now make their wishlist public and share it via a unique link. The link is generated with a default name of "<User>'s Wishlist".


### 🔧 Improved
- **Natural Sort** - Improved sorting logic for titles and authors to correctly handle numbers (e.g., "Vol 2" sorts before "Vol 10").


### 🐛 Fixed
- **Series Duplication** - Fixed an issue where assigning a book to an existing series would sometimes create a duplicate series entry instead of linking to the existing one.
- **Share Counts** - Fixed an issue where share book counts would display as 0 or be inaccurate due to race conditions or missing data fields.

---

## [1.3.1] - 2025-12-24
### ✨ Added
- **Book Details** - Added "Move to Wishlist" option in the "More" menu to send a book back to your wishlist (resets reading progress)

### 🔧 Improved
- **Add Book**
  - **Duplicate Prevention** - Added strict, aggressive duplicate prevention. It effectively normalizes titles (ignoring "Vol", "Volume", "Book", "Part") to catch matches like "The Boxer Vol 3" and "The Boxer 3", while correctly distinguishing distinct editions like "The Boxer Novel".
  - **Smart Search** - Search results now automatically filter out books you already own or have wishlisted. The system now fetches **80 books** per search to ensure you still get 40 relevant results even after filtering.
- **Library**
  - **Filter UX** - Removed redundant "Genre" filter (since dedicated page exists) and added scrolling to filter dropdowns for better handling of long lists
- **Add Book**
  - **Defaults** - "Format" field now defaults to "Paperback"
- **Search**
  - **Series Parsing** - Title search now prioritizes matching against your *existing* library series, preventing duplicate or mismatched series entries

### 🐛 Fixed
- **Navigation Scroll** - Fixed issue where pages would remain scrolled down after navigation (e.g., after adding a book to wishlist)

---

## [1.3.0] - 2025-12-23

### ✨ Added
- **Advance Shelf Management** - Comprehensive tools for organizing your shelves
  - **"Add Books" Page** - Dedicated page (`/shelves/[id]/add`) to bulk add books with filtering and local search
  - **Shelf Selection UI** - Persistent bottom bar for managing books within a shelf
    - Select Mode with "Select All" / "Deselect All" options
    - Bulk "Remove" and "Add to Another Shelf" actions
  - **Smart Creation** - "Add books immediately" option when creating a new shelf
- **Shelf Search** - Real-time client-side search bar within shelf details to find books by title or author


### 🔧 Improved
- **Library Features**
  - **In-Page Search** - Filter books by title, author, publisher directly in the library view
  - **Enhanced Selection** - "Select All" option, persistent selection state, and improved UI

### 🐛 Fixed
- **Shelf Filtering** - Fixed bug where viewing a shelf displayed all books from the library
- **Shelf Sorting** - Shelves are now correctly sorted alphabetically (case-insensitive)

---

## [1.2.0] - 2025-12-21

### ✨ Added
- **Categorized Search** - Search results now organized by type (Books, Authors, Series, Publishers, Genres, Shelves)
  - Click on authors, series, genres, and shelves to navigate directly to their pages
  - Search query persists in URL for easy back navigation
  - Unique entity names displayed instead of duplicate book listings
- **Page Animations** - Smooth slideIn animations for Genres and Series pages

### 🎨 Redesigned
- **Authors Page** - Complete visual overhaul with gradient avatars, glassmorphism cards, and circular progress indicators
  - Theme-based accent colors for consistent visual design
  - Smooth hover animations and micro-interactions
  - Responsive grid layout (1/2/3/4 columns)
- **Genres Page** - Masonry-style layout with alternating card sizes
  - Theme-based gradient backgrounds matching global accent color
  - Column-wise filling with alternating large/small pattern
  - Prominent book counts with decorative overlays
  - Multi-segment horizontal progress bars
  - Alphabetically sorted genre list
  - Fast slideIn animations (0.3s duration, 0.03s stagger)

### 🔧 Improved
- **Search Performance** - Faster categorized search with debouncing
- **Search UX** - Entity cards with icons and hover effects
- **Icon Consistency** - CheckCircle2 icon for completed books (replaced TrendingUp)
- **Card Sizing** - Icons maintain size with `shrink-0` class for long text
- **Mobile Experience** - Better touch interactions and responsive design
  - Genres page: Compact card heights on mobile (h-24/h-16 vs h-56/h-28 on desktop)
  - Reduced text sizes and spacing for mobile viewports
  - Hidden non-essential elements on small screens

### 🐛 Fixed
- **Genre Filtering** - Fixed genre detail page showing all books instead of filtered results
  - Removed Firestore query filter in favor of client-side filtering
  - Case-insensitive and whitespace-trimmed genre name matching
  - Proper handling of genre arrays
- **Search State Persistence** - Search query now persists when navigating back from results
- **Color Consistency** - Authors and Genres pages now use theme accent colors

---

# 📚 HonZuki v1.1.0 - Initial Public Release

Your personal book sanctuary is here! A feature-rich Progressive Web App 
for managing your physical book collection.

## 🌟 Highlights

- 📱 **Cross-Platform**: Web app (PWA) + Native Android APK
- 📖 **Complete Library Management**: Track 1000s of books
- 📊 **Series Management**: First-class series support with visual progress
- 🎨 **Beautiful Themes**: Adaptive backgrounds and custom colors
- 🔍 **Smart Search**: Find books by title, author, series, or genre
- 📦 **Offline Support**: Core features work without internet
- 🆓 **Free & No Ads**: Completely free, no subscriptions

---

### ⚠️ Known Issues / Current Status
- 🔴 **Authentication Disabled** - All users must use Guest Mode
- ❌ **No Cloud Sync** - Data stored locally only (in browser localStorage)
- ✅ **Sharing Features** - Public share links enabled for authenticated users
- ✅ **All Core Features Work** - Full functionality in Guest Mode
- 📋 **Export Regularly** - Back up your library via Settings → Export
- 🔜 **Authentication Fix Planned** - Expected in future release
