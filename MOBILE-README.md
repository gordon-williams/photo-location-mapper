# Photo Location Mapper - Mobile Version

A touch-optimized mobile web app for viewing photos and routes on a map.

**Live App:** https://gordon-williams.github.io/photo-location-mapper/mobile.html

## Features

### Photo Management
- Load photos from your device
- Automatic GPS extraction from EXIF data
- Photo gallery with GPS status badges (green = has GPS, red = no GPS)
- Fullscreen photo viewer with swipe navigation
- Photo details modal showing filename, date, and coordinates

### Route Display
- Load GPX and JSON route files
- Automatic activity type detection from file metadata
- Speed-based activity inference when type is unknown (walking, running, cycling, driving)
- Manual activity type selection for unrecognized routes
- Activity filter chips to show/hide route types
- Color-coded routes matching Arc app colors:
  - Walking: Green (#12A656)
  - Running: Orange (#EB781B)
  - Cycling: Blue (#039FD4)
  - Driving: Red (#E35641)
  - Bus/Train: Purple (#4056B5)
  - Flying: Violet (#7A3CFC)

### Map
- Street Map (OpenStreetMap)
- Satellite imagery (Esri)
- Humanitarian map style
- Photo markers with clustering
- Route polylines with white border for visibility
- Center map button to fit all markers

### Mobile-Optimized UI
- Bottom navigation bar (Photos / Map)
- Floating action button for adding content
- Full-screen modals for settings and photo viewing
- Touch-friendly controls
- Dark theme throughout

## Usage

1. **Add Photos**: Tap the + button in the Photos view to select images
2. **View on Map**: Switch to Map view to see photo locations
3. **Add Routes**: Tap the + button in Map view to load GPX/JSON files
4. **Filter Activities**: Use the chips at the bottom of the map to toggle route types
5. **Change Map Style**: Tap the layers button to select a different map

## Supported File Formats

### Photos
- JPEG with EXIF GPS data
- Any image format (displayed without location if no GPS)

### Routes
- **GPX files**: Standard GPS Exchange Format with tracks
- **JSON files**: Google Takeout Timeline format (Arc app export)

## Technical Details

- Single HTML file with inline CSS and JavaScript
- No build process required
- Uses Leaflet.js for mapping
- Uses ExifReader for GPS extraction
- Works offline after initial load (maps require internet)

## Version

Current: 1.0.0 (Build 138)

See [MOBILE-CHANGELOG.md](MOBILE-CHANGELOG.md) for version history.
