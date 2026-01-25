# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] - 2026-01-25 (Build 108)

### Added
- 3D terrain view with Mapbox GL JS
- Toggle between 2D and 3D map views
- 3D terrain exaggeration for enhanced visualization
- Balloon-style photo markers in 3D view (click number marker to reveal photo on string)
- Disney-style bouncy animation when balloon photo markers appear
- Reset button in 3D mode to re-center on all markers
- Route polylines displayed in 3D view with terrain draping
- Atmospheric sky rendering in 3D view
- View synchronization between 2D and 3D modes
- Independent size controls for 2D and 3D views
- 3D map style selector (Standard with 3D Buildings, Satellite Streets, Satellite, Outdoors, Streets)
- Mapbox Standard style with enhanced 3D buildings
- 3D building extrusions for Streets style (zoom 15+)
- Slider controls overlay on map for better UI layout
- Right-click drag to move photo markers (alternative to Alt+drag)
- Spread slider now works in 2D view for spider cluster distance
- BUILD file for tracking development builds
- GPX activity type inference from speed when no activity data present
- Activity type confirmation dialog for GPX files without activity data
- Elevation profile chart with interactive tooltip and map marker
- Elevation button on control bar to toggle elevation panel

### Changed
- Map resizes when elevation panel is toggled (fills available space)
- Swapped Alt/Option key behavior: default drag now pans image within marker, Alt+drag moves the marker
- Map Style dropdown dynamically shows 2D or 3D styles based on current view mode
- Photo Markers button tooltip updated to reflect new controls
- 3D view slider defaults changed to 280px and 2x for better visibility
- Mapbox API key button restyled to match other buttons (square, same height)
- All buttons now have visual mouse-down (active) states
- Removed emoji icons from buttons for cleaner UI
- Renamed buttons: "2D View" → "2D", "3D View" → "3D", "Reset View" → "Reset"
- Renamed "Save Map as JPEG" → "Save Map Image"
- Dark mode UI: black headers, dark grey control bars (#333), dark grey gallery background (#555)
- Photo marker Size slider now resizes circles dynamically during drag
- Transient messages now use dark grey background
- Click-to-confirm pattern for Clear All button (browser confirm() was being blocked)
- Claude Code-style status line with blinking cursor for loading/status messages
- № Size slider now resizes dynamically (badges are vector-based, no performance issue)

### Fixed
- Gallery JPEG export now properly handles object-fit (images no longer stretched)
- 3D view Save as JPEG now works using Mapbox canvas export (fixes CORS/WebGL issues)
- Photos in 3D view now correctly use transform settings from 2D editing (scaled by size ratio)
- Number marker hidden when photo balloon is displayed in 3D view
- Photo removal now immediately updates map markers in both 2D and 3D modes
- 3D activity filter now properly updates polylines when toggled
- 2D photo marker scroll zoom now enlarges from center (not top-left)
- Balloon photo marker positioning fixed (was appearing at top-left of map)
- Reset view now uses actual marker positions (including offsets) and visible polylines
- Route filtering: unchecking all activities now correctly hides all routes
- 3D route visibility updates properly when toggling activity filters
- 3D JPEG export now captures number markers and photo balloon markers
- Photo marker dynamic sizing now updates all nested DOM elements correctly
- Slider controls hidden when saving 2D map as JPEG
- Removed undefined `displaySavedPaths()` function call
- Google Takeout JSON parser now extracts altitude data for elevation chart
- GPX parser validates elevation values (rejects NaN)

### Performance
- Dynamic slider updates for photo marker circles (resize live during drag)
- For many photos (>5), images hidden during Size slider drag for performance
- Debounced slider inputs for number badges and spread (150ms delay)
- Throttled 3D marker depth updates during camera movement
- Lazy loading and async decoding for marker images
- GPU acceleration hints for smoother marker interactions

---

## [1.0.0] - 2026-01-24

### Added
- Initial public release
- Photo GPS extraction from JPEG EXIF data
- Interactive map display with multiple tile providers
- Photo Markers mode with draggable circular thumbnails
- Alt/Option + drag to pan image within photo marker
- Draggable number badges that orbit around photo markers
- Rubberband lines showing connection between moved markers and GPS location
- GPX route file import
- Google Takeout JSON route file import
- Activity type filtering for routes
- Map style options: Street, Satellite, Cycle, Humanitarian
- Mapbox integration (Streets, Outdoors, Satellite, Satellite Streets)
- Save Map as JPEG export
- Save Gallery as JPEG export
- Marker size slider (50-400px)
- Number badge size slider
- Session state persistence for map view
- Privacy-first design (all processing in browser)

### Technical
- Built with Leaflet.js for mapping
- ExifReader for EXIF parsing
- dom-to-image-more for image export
- Canvas renderer for polylines (better export compatibility)

---

## Version History Format

### Version Numbers (Semantic Versioning)
- **MAJOR.MINOR.PATCH** (e.g., 1.0.0)
- **MAJOR**: Breaking changes or significant new features
- **MINOR**: New features, backwards compatible
- **PATCH**: Bug fixes, backwards compatible

### Change Types
- **Added**: New features
- **Changed**: Changes to existing functionality
- **Deprecated**: Features to be removed in future
- **Removed**: Removed features
- **Fixed**: Bug fixes
- **Security**: Security-related changes
