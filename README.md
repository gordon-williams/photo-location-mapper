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

## Usage

1. Open `index.html` in a web browser (or host on GitHub Pages)
2. Click "Select Photos" or drag & drop photos onto the page
3. Photos with GPS data will be displayed in a grid with location information
4. Click "Show on Map" to visualize photo locations
5. Optionally import route data (GPX or JSON) to show your travel path
6. Use "Photo Markers" mode to display photo thumbnails on the map

## Map Styles

- **Street Map**: OpenStreetMap standard tiles
- **Satellite**: Esri World Imagery
- **Cycle Map**: CyclOSM with bike routes and contours
- **Humanitarian**: OpenStreetMap Humanitarian style
- **Mapbox** (API key required): Streets, Outdoors, Satellite, Satellite Streets

### Mapbox Setup

To use Mapbox map styles:
1. Sign up for a free account at [mapbox.com](https://www.mapbox.com/)
2. Copy your API key from your Mapbox account dashboard
3. Click the key icon next to the map style dropdown
4. Paste your API key

## Route File Support

### GPX Files
Standard GPX format from GPS devices and apps like Strava, Garmin, etc.

### Google Takeout JSON
Export your location history from Google Takeout and import the JSON files.

## Browser Compatibility

Works in modern browsers (Chrome, Firefox, Safari, Edge) with JavaScript enabled.

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Credits

- [Leaflet](https://leafletjs.com/) - Interactive maps
- [ExifReader](https://github.com/nicklockwood/ExifReader) - EXIF parsing
- [OpenStreetMap](https://www.openstreetmap.org/) - Map data
- [Mapbox](https://www.mapbox.com/) - Additional map styles

## Author

Gordon Williams

---

*Built with assistance from Claude AI*
