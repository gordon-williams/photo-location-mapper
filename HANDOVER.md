# Session Handover Document

## Project Overview

Photo Location Mapper is a browser-based tool that extracts GPS coordinates from photos and visualizes them on an interactive map. It's a single-file HTML application (`index.html`) with all CSS and JavaScript inline.

## Current State

- **Version**: 1.1.0
- **Build**: 90
- **Key Files**:
  - `index.html` - The entire application
  - `BUILD` - Contains current build number (increment with each change)
  - `CHANGELOG.md` - Version history
  - `README.md` - User documentation

## Recent Work (Builds 79-90)

### Build 79
- Fixed photo marker dynamic sizing - `updatePhotoMarkerSizes()` now updates all nested elements correctly
- Made number badge slider dynamic (was debounced) - badges are small/vector-based so no performance issue

### Build 80-81
- Fixed loading indicator dark background
- Rewrote 3D JPEG save to properly capture number markers and photo balloons

### Build 82
- Removed call to undefined `displaySavedPaths()` function

### Build 83
- Changed `.container` background from white to #555 (dark theme consistency)

### Build 84
- Hide slider controls when saving 2D map as JPEG

### Build 85
- Replaced browser `confirm()` with click-to-confirm pattern for Clear All button
- First click shows "Confirm?", second click performs clear
- Shift+click or double-click for instant clear

### Build 86
- Fixed route filtering: unchecking all activities now hides all routes (was showing all)
- Fixed 3D route visibility when toggling activity filters

### Build 87-88
- Added `:active` (mouse-down) states to all buttons throughout the app
- Activity selection modal, lightbox, photo delete, GPS buttons, gallery save, etc.

### Build 89-90
- Replaced elaborate loading spinner and error messages with simple status line
- Claude Code-style blinking cursor animation (▋)
- Monospace font, light grey text (#ddd) on dark background

## Key Architecture

### 2D View (Leaflet.js)
- Photo markers are circular thumbnails with draggable images inside
- Number badges orbit around photo markers
- Rubberband lines connect moved markers to original GPS positions
- Spider clusters spread overlapping photos

### 3D View (Mapbox GL JS)
- Requires Mapbox API key
- Shows numbered markers; click to reveal balloon-style photo on string
- Disney-style bounce animation when photos appear
- Uses `preserveDrawingBuffer: true` for JPEG export

### Status Line
- Single line below control bar with blinking cursor
- `setStatus(message, duration)` - show message, optional auto-clear
- `clearStatus()` - clear immediately
- `showError(message, type)` - legacy wrapper with auto-timeout

### Slider Controls
- **Size**: Photo marker diameter (50-400px) - dynamic resize
- **№ Size**: Number badge scale (0.5x-3x) - dynamic resize
- **Spread**: Spider cluster distance (2D only) - debounced

## Coding Conventions

1. **Always increment BUILD number** after each change
2. **Update CHANGELOG.md** for significant features/fixes
3. **Update HANDOVER.md** with recent work summary
4. **Dark mode UI**: Headers are black (#000), control bars are dark grey (#333), container/gallery background is #555
5. **No emoji icons** in buttons (removed in Build 69)
6. **All buttons need `:active` states** for mouse-down feedback

## How to Test

1. Open `index.html` in a browser
2. Select photos with GPS data
3. Click "Map" button
4. Enable "Photo Markers" mode
5. Test sliders - all should resize dynamically
6. Test Clear All - should show "Confirm?" on first click
7. Check status line appears during photo loading

## Notes for New Session

- Read `README.md` for full feature documentation
- Read `CHANGELOG.md` for version history
- Check `BUILD` file for current build number
- The application is entirely in `index.html` - search for function names to find code sections
- User prefers concise changes without over-engineering
- Browser `confirm()` dialogs may be blocked - use click-to-confirm pattern instead
