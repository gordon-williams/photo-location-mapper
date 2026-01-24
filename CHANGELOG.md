# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
