# Changelog

All notable changes to HonZuki will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2025-12-21 (Current Release)

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

### ⚠️ Known Issues / Current Status
- 🔴 **Authentication Disabled** - All users must use Guest Mode
- ❌ **No Cloud Sync** - Data stored locally only (in browser localStorage)
- ❌ **No Sharing Features** - Public share links disabled
- ✅ **All Core Features Work** - Full functionality in Guest Mode
- 📋 **Export Regularly** - Back up your library via Settings → Export
- 🔜 **Authentication Fix Planned** - Expected in future release

---

For detailed information about each release, see the [Releases](../../releases) page.
