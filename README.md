# Photo Location Mapper

A browser-based tool to extract GPS coordinates from photos and visualize them on an interactive map.

## Features

- **Photo GPS Extraction**: Extract GPS coordinates from JPEG photos with EXIF data
- **Interactive Map**: View photo locations on OpenStreetMap, Mapbox, or satellite imagery
- **Photo Markers**: Display photo thumbnails directly on the map with draggable positioning
- **Route Import**: Import GPX or Google Takeout JSON route files to show your travel path
- **Timeline Filtering**: Filter routes by activity type (walking, cycling, driving, etc.)
- **Export**: Save map views as JPEG images
- **Privacy-First**: All processing happens locally in your browser - no data uploaded to servers

## Quick Start

1. Open the app in a web browser
2. Click **Select Photos** or drag & drop photos onto the page
3. Photos with GPS data will be displayed in a grid with location information
4. Click **Show on Map** to visualize photo locations
5. Optionally click **Load Route** to import GPX or JSON route data
6. Click **Photo Markers** to display photo thumbnails on the map

## Photo Markers Mode

When Photo Markers mode is enabled, your photos appear as circular thumbnails on the map instead of numbered pins.

### Controls

| Action | How |
|--------|-----|
| **Pan image within marker** | Drag inside the photo circle |
| **Move photo marker** | Hold **Alt/Option** + drag, or **right-click drag** the circular photo marker |
| **Move number badge** | Drag the numbered badge to orbit around the photo |
| **Resize markers** | Use the **Size** slider |
| **Resize number badges** | Use the **№ Size** slider |
| **Adjust cluster spread** | Use the **Spread** slider (2D view only) |

### Rubberband Line

When you drag a photo marker away from its original GPS location, a dashed rubberband line appears connecting the marker to a dot showing the actual GPS position. This helps you remember where the photo was really taken while arranging markers for a cleaner layout.

## Map Controls

### Map Styles

- **Street Map**: OpenStreetMap standard tiles
- **Satellite**: Esri World Imagery
- **Cycle Map**: CyclOSM with bike routes and contours
- **Humanitarian**: OpenStreetMap Humanitarian style (default)
- **Mapbox styles** (API key required):
  - Mapbox Streets
  - Mapbox Outdoors
  - Mapbox Satellite
  - Mapbox Satellite Streets

### Navigation

- **Zoom**: Mouse scroll wheel or +/- buttons
- **Pan**: Click and drag the map
- **Click photo marker**: Opens a popup with photo details

## Route Import

Click **Load Route** to import route/track data that shows your travel path on the map.

### Supported Formats

#### GPX Files
Standard GPX format exported from:
- GPS devices (Garmin, etc.)
- Fitness apps (Strava, Komoot, etc.)
- Mapping apps

#### Google Takeout JSON
Location history exported from Google:
1. Go to [Google Takeout](https://takeout.google.com/)
2. Select "Location History"
3. Export and download
4. Import the JSON files

### Activity Filtering

When route data includes activity types (walking, cycling, driving, etc.), checkboxes appear allowing you to show/hide specific activities. Stationary periods are automatically filtered out.

## Saving Maps

Click **Save Map Image** to export the current map view as an image. The export includes:
- Map tiles
- Route lines
- Photo markers (if enabled)
- Number badges
- Rubberband lines

*Note: Some satellite tile providers may block image export due to CORS restrictions. If export fails, try switching to Street or Cycle map.*

## Mapbox Setup

Mapbox provides high-quality map tiles and 3D terrain with a generous free tier (50,000 map loads/month).

1. Sign up at [mapbox.com](https://www.mapbox.com/)
2. Copy your API key from the account dashboard
3. In Photo Location Mapper, click the 🔑 button next to the map style dropdown
4. Paste your API key
5. Select a Mapbox style from the dropdown, or use the 3D View

Your API key is stored locally in your browser and persists across sessions.

## 3D Terrain View

With a Mapbox API key configured, you can view your photos and routes in 3D terrain:

1. Configure your Mapbox API key (see above)
2. Click the **3D** button
3. The map switches to 3D with terrain elevation
4. Navigate using mouse drag to pan, scroll to zoom, right-drag to rotate/tilt
5. Click **2D** to return to the standard view

### 3D View Features
- Realistic terrain elevation with 1.5x exaggeration
- Multiple map styles: Satellite Streets, Satellite, Outdoors (with contour lines), Streets
- Atmospheric sky rendering
- Numbered photo location markers
- Balloon-style photo display with bouncy animation (click a number marker to reveal the photo)
- Route polylines following terrain with activity type filtering
- Independent size controls (separate from 2D settings)
- Reset button to re-center on all markers when lost
- Save as JPEG export
- View position syncs when switching between 2D and 3D

### 3D Photo Markers

In 3D view, photos are displayed differently than in 2D:
- Photo locations show as numbered markers
- Click a number marker to reveal the photo in a balloon above it
- Click the photo balloon to dismiss it
- Photo positioning from 2D editing is preserved
- Size sliders control 3D markers independently from 2D

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| **Drag** | Pan image within photo marker circle |
| **Alt/Option + Drag** | Move photo marker to new position |
| **Right-click + Drag** | Move photo marker to new position (alternative) |
| **Scroll wheel** | Zoom image within photo marker (zooms from center) |

## Tips

- **Overlapping photos**: Use Photo Markers mode and drag markers apart for clearer visibility
- **Large photo collections**: Use the size slider to make markers smaller
- **Route context**: Import your route data to see the path you took between photos
- **Best export quality**: Position the map exactly how you want it before saving as JPEG

## Privacy

All processing happens entirely in your browser:
- Photos are never uploaded to any server
- GPS data is extracted locally using JavaScript
- Route files are parsed locally
- Your Mapbox API key is stored only in your browser's localStorage

## Browser Compatibility

Works in modern browsers with JavaScript enabled:
- Chrome (recommended)
- Firefox
- Safari
- Edge

### Known Issue: macOS File Dialog Focus

On macOS, when the file picker opens, you may need to click once inside the dialog before you can select files. Similarly, after closing the file picker, you may need to click once on the browser window to restore focus before interacting with other elements. This is a quirk of how browsers interact with native macOS file dialogs, not a bug in the application.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for version history and release notes.

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Credits

- [Leaflet](https://leafletjs.com/) - Interactive maps
- [ExifReader](https://github.com/mattiasw/ExifReader) - EXIF parsing
- [OpenStreetMap](https://www.openstreetmap.org/) - Map data
- [Mapbox](https://www.mapbox.com/) - Additional map styles
- [dom-to-image-more](https://github.com/1904labs/dom-to-image-more) - Map export

## Author

Gordon Williams

---

*Built with assistance from Claude AI*
