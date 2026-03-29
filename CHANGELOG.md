# Changelog

All notable changes to HonZuki will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [2.17.0] - 2026-03-29
### ✨ Added
- **Social identity system** - Added unique `@username` for each user alongside display name for public identity and friend discovery.
- **Copy username button** - Added icon-only copy button on profile header (shows check icon on success) to quickly copy username handle.
- **Friends page** - Implemented fully functional Friends hub with three tabs: Find Friends (search), Friends list, and Friend Requests (incoming).
- **Username search with exact matching** - Added secure username search with exact-match-only mode triggered by search button (or Enter key) to prevent accidental requests to wrong users.
- **Friend request system** - Added bidirectional friend request flow: send requests, accept/reject incoming requests, and remove friends.
- **Relationship status display** - Profile header now shows user's relationship status with visitors (Friends badge, Request Pending, or Add Friend button).
- **View profile button** - Added "View Profile" button in username search results alongside "Add" button for safer friend discovery.
- **Username normalization script** - Added admin tool to normalize existing user usernames for consistency (3-30 chars, lowercase, safe charset). Supports `--dry-run` flag.

### ♻️ Changed
- **Profile identity split** - Separated profile display name (free-form) from unique @username (handle) across all UI.
- **Public profile URLs** - Switched from UID-based `/p/[userId]` to username-based `/p/[username]` with legacy UID fallback.
- **Profile architecture** - Removed `public_profile_shares` collection entirely - all profiles are now public by default without requiring share action.
- **Firestore schema** - Added `usernameLower` field to public_profiles and created new `profile_usernames` collection for unique username claims.
- **Search UX** - Changed from live-as-you-type search to explicit search button for username lookup to improve security and intent clarity.
- **Reading time format** - Updated reading time display to show days, hours, and minutes (e.g., "2d 3h 45m") for better granularity.

### 🐛 Fixed
- **Firestore permissions** - Updated friend_requests and friends collection read rules to allow existence checks via `get`/`list` operations for authenticated users.
- **Username claim enforcement** - Implemented transactional username assignment at profile creation and update to ensure uniqueness.
- **Relationship lookups** - Fixed friend request and friendship existence checks to support bidirectional relationship queries.
- **Profile stats accuracy** - Fixed pages read and reading time calculations on profile stats cards to match stats page exact same logic and behavior, including using global reading speed preference and proper effective reading speed calculation.

### 🔒 Security / Rules
- Added/updated Firestore rules for `friend_requests` collection (send/receive/respond operations).
- Added/updated Firestore rules for `friends` collection (apply-after-request-accepted, bidirectional management).
- Added/updated Firestore rules for `profile_usernames` collection (owner-managed unique claims).
- Removed rules for deprecated `public_profile_shares` collection.
- Changed public_profiles read from gated to public-readable.
- Added `get`/`list` permissions for authenticated users to support existence checks during friend operations.

### 🧪 Data / Ops
- Executed username normalization for all existing user profiles (4 profiles processed).
- Verified username claim system atomic enforcement via Firestore transactions.
- Validated production build and deployed updated Firestore rules.

---

## [2.16.0] - 2026-03-28
### ✨ Added
- **Achievements platform rollout** - Added full achievements feature set with tier/category definitions, unlock detection, unlock toasts, dedicated achievements index/detail pages, and home/profile achievement surfacing.
- **Locked-achievement progress UI** - Added per-achievement progress display on achievement detail pages for not-yet-unlocked achievements.
- **Achievement state tracking** - Added user achievement state support for latest unlock, recent unlock list, and viewed status handling.
- **Public profile sharing** - Added shareable public profile links, profile share action, and dedicated public profile route (`/p/[shareId]`).
- **Unified public profile rendering** - Added public-view mode using the same profile renderer as signed-in profiles for visual parity.
- **Profile XP/Level module** - Added reusable XP/level utility layer and integrated it into profile header rendering.
- **Circular level avatar** - Added reusable circular progress avatar with level badge for profile identity/progression display.
- **Historical achievement reconciliation script** - Added admin script to backfill historically accurate unlock dates for existing achievement records.

### ♻️ Changed
- **Profile achievements behavior** - Changed profile achievements from "recent only" to showing all unlocked achievements.
- **Profile labeling** - Non-own profile titles now display as "<username>'s Profile" for clearer ownership context.
- **Friends surface status** - Friends page now explicitly displays "Coming Soon" while social interactions are staged.
- **Sidebar IA** - Reordered navigation below Stats to `Profile → Achievements → Friends`.
- **Share behavior by platform** - On Windows, profile share now directly copies link; on other platforms native share is used when available.
- **Relationship CTA behavior** - Non-own profile header now shows disabled "Send Friend Request" state to avoid unfinished-flow actions.
- **XP economy redesign** - Rebalanced XP sources to event-based rewards: book add (+5), book start (+10 once per book), book completion (+20), series completion (+40), every 100 pages (+15), and tier-based achievement XP (basic +60, advanced +120, elite +250).
- **Level progression redesign** - Updated progression curve and raised cap to level 30 with tuned early/mid/late/endgame scaling.
- **Post-cap progression behavior** - XP beyond cap now remains visible as banked XP and is retained for future level-cap increases.

### 🐛 Fixed
- **Historical unlock-date accuracy** - Fixed legacy achievements with inaccurate unlock chronology by reconciling from historical reading/shelf/series activity.
- **Public profile data gaps** - Fixed public profiles not loading currently reading, avatar, and shelves in some cases.
- **Public/shared read access** - Fixed permission/rule gaps affecting public profile and shared profile data reads.
- **Public profile parity regressions** - Fixed mismatches between private and public profile rendering paths.
- **Share UX reliability on Windows** - Fixed inconsistent share flow by enforcing clipboard-first behavior on Windows.

### 🔒 Security / Rules
- Added/updated Firestore rules for `public_profile_shares` schema validation and active-share-gated reads.
- Extended rule coverage for public/shared profile rendering, including profile-related subcollections and achievements read paths.

### 🧪 Data / Ops
- Executed achievement unlock-date reconciliation in dry-run and live modes with expected unlock document updates.
- Verified production build success and deployed updated Firestore rules.

---

## [2.15.0] - 2026-03-26
### ✨ Added
- **Series index** - Modernized series listing with compact cards, fixed-size icon containers, and clearer stat tiles showing Read / Owned / Total counts. Removed the top accent strip, footer chevrons, and the redundant progress header for a cleaner, more compact layout.
- **Shelves index** - Modernized shelves listing with a create panel, in-page search, and redesigned shelf cards. Removed the "Build Your Reading Zones" hero card to reduce visual clutter.
- **Subshelves** - Added nested subshelves under shelves with create, rename, delete, and book assignment support.
- **Subshelf add-books flow** - Added dedicated route for managing subshelf membership (`/shelves/[id]/subshelves/[subshelfId]/add-books`).
- **Shelf-specific book actions** - Added per-book quick actions on shelf cards to remove from shelf, remove from current subshelf, and add to another subshelf.
- **Shelf icon system** - Added user-selectable shelf icons for create/edit flows and rendering across shelves and sharing surfaces.
- **Icon picker expansion** - Added categorized Iconify-based icon options while preserving the default Lucide shelf icon.
- **Publisher sharing** - Added new `publisher` share type across create, edit, public, and count/update logic.
- **Shelf share visibility controls** - Added per-subshelf visibility toggles for shelf shares, including public-page filtering.

### ♻️ Changed
- Unified card layout and icon sizing between Series and Shelves for consistent alignment and improved readability across pages.
- Redesigned shelf details with a cleaner, category-style layout (stats card, subshelf management section, improved controls).
- Updated shelf and subshelf book ordering to natural alphabetical sorting for consistent browsing.
- Improved back-navigation behavior in add flows by using history-aware navigation.
- Enhanced share creation step UI to a cleaner two-column option layout and improved selected/hover icon states.
- Updated shelf CSV export/import compatibility to include optional shelf icon data.

### 🐛 Fixed
- Removed visual clutter by removing the series card top accent strip and the Shelves hero card.
- Fixed runtime error caused by stale `ManageSubshelfBooksDialog` references on shelf details.
- Fixed event propagation on shelf book action menus that could navigate to book details unintentionally.
- Fixed Firestore permission issues for subshelf creation and validation edge cases for new share/shelf fields.
- Fixed icon picker dialog overflow issues by constraining dialog body and enabling proper internal scrolling.
- Fixed step-1 share option icon hover inversion so icons follow card hover foreground styling.

### 🧹 Cleanup
- Removed deprecated/unused subshelf dialog implementation replaced by the dedicated add-books page flow.
- Removed temporary debug logging and unused imports introduced during subshelf implementation.

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
