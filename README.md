# 📚 HonZuki: Your Personal Book Sanctuary

> A modern Progressive Web App (PWA) for managing your physical book collection with cloud sync, reading progress tracking, and beautiful adaptive themes.

[![Version](https://img.shields.io/badge/version-1.1.0-blue)](https://github.com/YTFL/HonZuki-BookTracker)
[![Next.js](https://img.shields.io/badge/Next.js-16.0-black)](https://nextjs.org/)
[![Firebase](https://img.shields.io/badge/Firebase-11.9-orange)](https://firebase.google.com/)
[![License](https://img.shields.io/badge/license-Freeware-green)](LICENSE)
[![PWA](https://img.shields.io/badge/PWA-enabled-blueviolet)](https://web.dev/progressive-web-apps/)

---

## 🌐 Access the App

**Web App**: [https://hon-zuki.vercel.app](https://hon-zuki.vercel.app)

**Android App**: Download [HonZuki.apk](./HonZuki.apk) and install on your Android device

---

## 📖 About

HonZuki is a feature-rich book management application designed for book lovers who want to organize their physical book collection digitally. Track your reading progress, organize books into custom shelves, manage series, and sync everything across all your devices.

### Why HonZuki?

- 📱 **Cross-Platform**: Works on web, iOS, and Android
- 📊 **Reading Analytics**: Track your reading habits and progress
- 🎨 **Beautiful Design**: Adaptive themes that match your book covers
- 🔍 **Smart Search**: Find books by title, author, series, or genre
- 🆓 **Free & Open**: No subscriptions, no ads

---

## ✨ Complete Feature List (Every Single Feature!)

### 📚 Library Management
- ✅ **Multiple View Modes**
  - Grid view with 2, 3, 4, 5, or 6 columns (adjustable)
  - List view with detailed information
- ✅ **Adding Books**
  - ISBN barcode scanner using camera
  - Search using book title
  - Manual book entry with comprehensive form
  - Smart series detection from book titles
- ✅ **Book Information Tracking**
  - Title (required)
  - Multiple authors support (add unlimited authors)
  - ISBN-10 and ISBN-13
  - Cover image (auto-fetch or manual upload)
  - Series name and number in series
  - Multiple genres (select as many as needed)
  - Publisher name
  - Page count
  - Publication year
  - Book format (paperback, hardcover, ebook, audiobook)
  - Language
  - Custom cover image URL
  - Date added (automatically tracked)
- ✅ **Reading Progress Tracking**
  - 5 reading statuses: Unread, Reading, Completed, On Hold, Dropped
  - Current page number tracking
  - Visual progress percentage bar
  - Start date (with calendar picker or "unknown" option)
  - Finish date (with calendar picker or "unknown" option)
  - Progress displayed on book cards and list items
- ✅ **Favorites System**
  - Star/unstar books as favorites
  - Heart icon toggle on book cards
  - Dedicated favorites page
  - Filter library by favorites
  - Visual indicator on book covers
- ✅ **Custom Shelves**
  - Create unlimited custom shelves
  - Add books to multiple shelves simultaneously
  - Remove books from shelves
  - Delete entire shelves
  - Rename shelves
  - View all books on a specific shelf
  - Filter library by shelf selection
- ✅ **Bulk Operations**
  - Selection mode toggle
  - Select all books option
  - Clear selection option
  - Bulk delete selected books
  - Visual selection indicator (checkboxes)
  - Selected count display
- ✅ **Book Details Page**
  - Large cover image display
  - All book information displayed
  - Edit button to modify details
  - Delete button with confirmation
  - Adaptive background colors from cover
  - Reading speed estimate (time to finish)
  - Individual book reading speed override
  - Series information with link
  - Genre tags with links
  - Author links
  - Shelf badges
  - Quick status change dropdown
  - Page number input with slider
  - Date pickers for start/finish dates
  - Favorite toggle
  - Shelf selector with checkboxes
  - Visual polish with smooth transitions
- ✅ **Book Editing**
  - Edit all book details
  - Form validation
  - Auto-save draft (session storage)
  - Series auto-complete suggestions
  - Genre multi-select
  - Format dropdown
  - Cover image preview
  - Cancel and save buttons

### 📖 Series Management
- ✅ **Series Entity System**
  - Series as first-class database entities
  - Dedicated series pages with all books
  - Series list page showing all series
  - Clickable series names throughout app
- ✅ **Auto-Tracked Statistics**
  - Total books owned in series
  - Total books read (completed)
  - Books currently reading count
  - Automatic updates on book changes
- ✅ **Visual Progress Tracking**
  - Multi-segment progress bar
  - Read books shown in full accent color
  - Owned but unread shown in lighter shade
  - Not owned books shown as empty
  - Percentage completion displayed
- ✅ **Series Information**
  - Series title
  - Total books planned in series
  - Series status (Ongoing or Completed)
  - Missing books indicator
  - Books owned vs total ratio
  - Reading progress percentage
- ✅ **Series Management Actions**
  - Create new series from add/edit book form
  - "+1 Book Released" button for ongoing series
  - Edit series details (title, total, status)
  - Delete series
  - Smart prompts when adding series books
  - Series auto-complete in book forms
- ✅ **Series Statistics Cards**
  - Collection progress card (owned/total)
  - Reading progress card (read/owned)
- ✅ **Series Book Display**
  - All books in series shown on series page
  - Books sorted alphabetically by title
  - Grid or list view options
  - Book cards with progress indicators
  - Filter and search within series

### 📊 Statistics & Analytics
- ✅ **Comprehensive Stats Dashboard**
  - Total books owned
  - Total pages in library
  - Total pages read
  - Number of authors in collection
  - Number of genres tracked
  - Number of series
  - Completion rate percentage
- ✅ **Genre Distribution Chart**
  - Donut chart showing genre breakdown
  - Top 5 genres plus "Other" category
  - Color-coded segments
  - Interactive hover with counts
- ✅ **Collection Metrics Cards**
  - Total books card with icon
  - Pages read card with progress
  - Authors count card
  - Series count card
  - Genres count card
  - Completion rate card with visual bar
  - Color-themed cards
- ✅ **Reading Speed Configuration**
  - Set global reading speed (pages per hour)
  - Configure in settings page
  - Used for time-to-read estimates
  - Per-book reading speed override option
- ✅ **Year-Based Stats**
  - View stats for specific years
  - Lifetime stats view
  - Books completed per year
  - Pages read per year
  - Year selector dropdown
- ✅ **Additional Stats**
  - Books by reading status (completed, reading, unread, etc.)
  - Format distribution (paperback, hardcover, ebook, audiobook)
  - Language distribution
  - Series completion rates
  - Reading time calculations
  - Stats update in real-time

### 🔍 Discovery & Browsing
- ✅ **Advanced Search System**
  - Global search across all books
  - Search by title, author, series, or publisher
  - Real-time search results
  - Debounced search for performance
  - Search result highlighting
  - Clear search button
  - Recent searches saved locally
- ✅ **Multi-Level Filtering**
  - Filter by reading status (Unread, Reading, Completed, On Hold, Dropped)
  - Filter by favorites only
  - Filter by custom shelves (multi-select)
  - Filter by genres (multi-select)
  - Filter by publishers (multi-select)
  - Filter by book formats (paperback, hardcover, ebook, audiobook)
  - Filter by languages
  - Filter by publication decades (1950s, 1960s, etc.)
  - Filter by page count ranges (0-100, 101-300, 301-500, 500+)
  - Filter by unknown start dates
  - Filter by unknown finish dates
  - Active filter chips with close buttons
  - Clear all filters button
  - Filter count badge
- ✅ **Advanced Sorting**
  - Sort by date added (newest/oldest)
  - Sort by title (A-Z/Z-A)
  - Sort by author (A-Z/Z-A)
  - Sort by reading progress (high to low/low to high)
  - Sort by page count (most/least)
  - Sort preferences saved per session
  - Multi-level sort menu
  - Current sort indicator
- ✅ **Browse by Category**
  - Dedicated Authors page listing all unique authors
  - Dedicated Genres page listing all genres
  - Dedicated Series page listing all series
  - Click any author/genre/series to see related books
  - Author pages show all books by that author
  - Genre pages show all books in that genre
  - Series pages show all books in series
  - Count badges showing number of items
- ✅ **Genre Management**
  - Rename genres directly from genre page
  - Delete genres with confirmation
  - Merge genre functionality
  - Genre count on genre cards
  - Genre color badges
- ✅ **Home Dashboard**
  - Recently added books section
  - Currently reading books section
  - Quick stats overview

### 📱 Wishlist Management
- ✅ **Separate Wishlist System**
  - Dedicated wishlist page
  - Add books to wishlist (not library)
  - Same rich metadata as library books
  - Cover images and full details
  - Series and genre support
- ✅ **Easy Migration**
  - "Move to Library" button on wishlist books
  - One-tap promotion from wishlist to library
  - Automatic data transfer
- ✅ **Full Metadata Support**
  - All book fields available
  - ISBN tracking
  - Series information
  - Multiple genres
  - Publisher and publication year
  - Format and language
- ✅ **Wishlist Actions**
  - Edit wishlist books
  - Delete from wishlist
  - View wishlist book details
  - Grid and list views
  - Search wishlist
  - Filter wishlist items
- ✅ **Visual Design**
  - Distinct wishlist badge
  - Same beautiful card design
  - Hover effects
  - Responsive layout
  - Loading states

### 🔄 Sharing Features
- ⚠️ **Currently Unavailable** - Sharing features require authentication (disabled until login is available)
- 🔜 **Coming Soon** - Once authentication is restored:
  - Public share links to your collections
  - Share entire library, specific shelves, or series
  - Share by author or genre
  - Create custom selections
  - Visibility control for individual books
  - Beautiful public-facing share pages with grid/list views
  - Search functionality on share pages
  - Edit and update shared collections anytime
  - Share link management
  - Active/inactive share toggles
  - Share description and titles

### 💾 Data Management
- ⚠️ **Local Storage Only** - Currently all data saved in browser's localStorage (no cloud sync)
- ✅ **Import Data**
  - Import from CSV files
  - Import from JSON files
  - File format validation
  - Preview import data
  - Import progress indicator
  - Support for books, wishlist, and series
  - Import settings and themes
- ✅ **Export Data**
  - Export library to CSV format
  - Export library to JSON format
  - Export wishlist separately
  - Export series information
  - Export settings and theme
  - Timestamp in filename
  - **Regular backups highly recommended!**
- ✅ **Data Management Page**
  - Import section with file picker
  - Export section with format options
- ⚠️ **Current Limitations**
  - No cross-device sync (device-specific)
  - No cloud backup
  - Data lost if browser data cleared
  - No automatic backups
  - Export regularly as backup strategy!
- 🔜 **Coming with Authentication**
  - Real-time cloud sync across devices
  - Automatic cloud backups
  - Data integrity checks
  - Conflict resolution
  - Version history

### 🔐 Account & Authentication
- ⚠️ **Guest Mode ONLY** - All users must currently use guest mode (login disabled)
- ⚠️ **No Database Storage** - Data NOT saved to database currently
- ✅ **Full Functionality** - All core features work in guest mode
- ✅ **Local Browser Storage** - Data saved securely in your browser's localStorage
- ❌ **Login/Registration Disabled** - Authentication features temporarily unavailable
- 🔜 **Coming Soon** - Account features will be restored in a future update:
  - Email/password authentication
  - Profile management
  - Display name configuration
  - Password change with re-authentication
  - Email updates with verification
  - Guest account conversion to full account
  - Multi-device sync
  - Cloud backup

### 🎨 Theme Customization
- ✅ **Accent Colors**
  - Solid color picker with hex input
  - Custom gradient builder
  - Multi-stop gradients (2-5 color stops)
  - Gradient angle control (0-360°)
  - Add/remove gradient stops
  - Fallback color for gradients
  - Live color preview
  - Recent colors history
  - 20+ preset colors
- ✅ **Background Colors**
  - Solid background color picker
  - Custom background gradients
  - Multi-stop gradients for backgrounds
  - Angle control for background gradients
  - Fallback color setting
  - Transparency options
  - Live background preview
  - Preset background gradients
- ✅ **Theme Import/Export**
  - Export theme to JSON file
  - Import theme from JSON file
  - Share themes with others
  - Theme validation on import
- ✅ **Advanced Options**
  - Reset theme to defaults
  - Custom hex color input
  - Color picker with saturation/lightness
  - Theme persistence across sessions

### 🖼️ Adaptive Backgrounds
- ✅ **Dynamic Book Cover Colors**
  - Automatically extract vibrant colors from book covers
  - Apply colors to book detail page backgrounds
  - Smooth color transitions
- ✅ **Lighten Filter**
  - Option to lighten extracted colors
  - Toggle on/off per preference
- ✅ **Darken Filter**
  - Option to darken extracted colors
  - Toggle on/off per preference
- ✅ **Adaptive Settings**
  - Global enable/disable toggle
  - Per-page color extraction
  - Settings saved per user

### 🔤 Typography
- ✅ **14 Built-in Font Families**
  - PT Sans (default)
  - Akaya Kanadaka
  - Courier New
  - IBM Plex Mono
  - Kalam
  - Literata
  - Manrope
  - Merriweather
  - Nunito
  - OpenDyslexic (dyslexia-friendly)
  - Recursive
  - Roboto Slab
  - Times New Roman
  - Wingdings
- ✅ **Custom Font Upload**
  - Upload your own font files (.ttf, .otf, .woff, .woff2)
  - Saved fonts appear in "My Fonts" section
  - Delete custom fonts anytime
- ✅ **Font Selection**
  - Dropdown selector with live preview
  - Fonts organized by system and custom
  - Applied instantly across entire app
  - Persistent font selection
- ✅ **Text Customization**
  - Text color picker (solid or gradient)
  - Text outline with adjustable color and width
  - Text shadow with blur, X/Y offset controls
  - Enable/disable outline and shadow independently
  - Real-time preview of all changes

### 📱 Progressive Web App
- ✅ **Install as Native App**
  - Install on iOS (Add to Home Screen)
  - Install on Android (Install app)
  - Install on Desktop (Chrome, Edge, Brave)
  - Custom app icon
  - Splash screen
  - Full-screen mode
  - Native app appearance
- ✅ **PWA Features**
  - App theme color
  - Responsive design
  - Touch-optimized
- ✅ **Native Experience**
  - Full-screen app mode
- ✅ **Automatic Updates**
  - Always get latest version
  - Seamless update experience
- ⚠️ **No Cloud Sync** - Currently device-specific (export data for backups)

---
- ⚠️ **Guest Mode ONLY** - All users must currently use guest mode (login disabled)
- ⚠️ **No Database Storage** - Data NOT saved to database currently
- ✅ **Full Functionality** - All core features work in guest mode
- ✅ **Local Browser Storage** - Data saved securely in your browser's localStorage
- ❌ **Login/Registration Disabled** - Authentication features temporarily unavailable
- 🔜 **Coming Soon** - Account features will be restored in a future update

---

## 🚀 Installation

### 📱 Android APK

1. Download [HonZuki.apk](./HonZuki.apk) from this repository
2. Enable "Install from Unknown Sources" in your Android settings
3. Open the APK file and follow installation prompts
4. Launch HonZuki from your app drawer

### 🌐 Progressive Web App (iOS, Desktop, Android)

1. Visit the web app at your deployment URL
2. **On iOS**: Tap Share → Add to Home Screen
3. **On Android**: Tap menu → Install app
4. **On Desktop**: Click install icon in address bar

The PWA works offline and provides a native app experience!

---

## 📱 Screenshots

*Note: Add screenshots of your app here to showcase the interface*

---

## 🛠️ Technology Stack

- **Frontend Framework**: Next.js 16.0 with App Router
- **UI Library**: React 18.3
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Components**: shadcn/ui
- **Icons**: Lucide React
- **Backend**: Firebase 11.9
  - Firestore (Database)
  - Authentication
  - Hosting
- **PWA Support**: @ducanh2912/next-pwa
- **Form Management**: react-hook-form + zod
- **Color Extraction**: node-vibrant
- **Barcode Scanning**: html5-qrcode
- **Date Utilities**: date-fns

---

## ⚠️ Important: Current Limitations

### 🔴 ALL USERS MUST USE GUEST MODE

**Authentication is currently disabled.** Everyone uses the app as a guest user.

#### What This Means:
- ❌ **No login or registration** - Authentication features are disabled
- ❌ **No cloud storage** - Data is NOT saved to Firebase database
- ❌ **No cloud sync** - Your data won't sync across devices
- ❌ **Sharing features disabled** - Cannot create public share links
- ✅ **All core features work** - Add books, track reading, organize library
- ✅ **Data saved locally** - Securely stored in your browser's localStorage
- ✅ **Works offline** - Fully functional without internet

#### 💡 Current Workflow:
1. Use the app normally - all features work!
2. **Export your library regularly** (Settings → Export) as backup
3. Keep export files safe
4. When authentication is fixed, you can import your data

#### ⚠️ Important Warnings:
- **Clearing browser data = losing your library!** Export regularly!
- **Data is device-specific** - Won't transfer to other devices
- **Use same browser** - Data doesn't transfer between browsers on same device

**Status**: We're actively working on fixing authentication. Expected in v1.2.0 update.

### Other Known Limitations

- ISBN scanner requires HTTPS (camera access restriction)
- Barcode scanning may not work on all devices or browsers
- Some ISBN lookups may fail due to external data source availability
- Large libraries (1000+ books) may experience slower load times

---

## 🗺️ Roadmap

### 🔧 Coming Soon
- [ ] **Fix authentication system**
- [ ] Reading goals and challenges
- [ ] Book recommendations based on reading history
- [ ] Enhanced statistics and analytics
- [ ] Book reviews and ratings
- [ ] Reading notes and highlights

### 🔮 Future Features
- [ ] Social features (follow friends, share reviews)
- [ ] Book clubs and group reading
- [ ] Export to Goodreads/LibraryThing
- [ ] Bulk ISBN import
- [ ] Enhanced mobile app with React Native

---

## 🤝 Contributing

While the source code is not publicly available, you can contribute by:

- 🐛 Reporting bugs and issues
- 💡 Suggesting new features
- 📖 Improving documentation
- 🌍 Helping with translations
- ⭐ Starring the repository if you like the app

Open an issue on GitHub to get started!

---

## 📄 License

This application is provided as **freeware** for personal and non-commercial use.

**You may:**
- ✅ Use the app for free
- ✅ Share the APK file with others
- ✅ Install on multiple devices

**You may not:**
- ❌ Modify or reverse engineer the application
- ❌ Use for commercial purposes without permission
- ❌ Remove copyright notices

See the [LICENSE](LICENSE) file for complete terms and conditions.

**Note:** The source code is not included in this repository and remains proprietary.

---

## 👨‍💻 Author

**YTFL**
- GitHub: [@YTFL](https://github.com/YTFL)

---

## 💬 Support

Need help or have questions?

- 📫 Open an issue on GitHub
- 📚 Check the documentation in this README
- 🔍 Review closed issues for solutions

---

## 🙏 Acknowledgments

Built with amazing open-source technologies:
- [Next.js](https://nextjs.org/) - The React framework for production
- [Firebase](https://firebase.google.com/) - Backend infrastructure
- [shadcn/ui](https://ui.shadcn.com/) - Beautiful component library
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Lucide](https://lucide.dev/) - Beautiful icon library
- [Vercel](https://vercel.com/) - Deployment platform

---

## ⭐ Star History

If you find HonZuki useful, please consider giving it a star! ⭐

---

**Made with ❤️ for book lovers, by a book lover**

*Happy Reading!*