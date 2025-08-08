# Map Creator Development Instructions

**ALWAYS reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.**

## Project Overview
Map Creator is a single-file HTML web application that creates an interactive floorplan map editor. Users can add draggable circle buttons to rooms, attach media files (images, videos, documents) to each button, and export the final map.

## Working Effectively

### Serving the Application
- **REQUIRED**: Serve the application via HTTP server. DO NOT open `map-creator.html` directly in browser (file:// protocol will not work correctly)
- Start HTTP server: `cd /path/to/repository && python3 -m http.server 8000`
- Access application: `http://localhost:8000/map-creator.html`
- Server startup is instant - no build time required

### Repository Structure
```
map-creator/
├── README.md           # Project requirements and description
├── map-creator.html    # Complete application (HTML, CSS, JavaScript)
└── .github/
    └── copilot-instructions.md
```

### No Build Process Required
- **Critical**: This repository has NO build system, package managers, or dependencies
- NO `npm install`, `pip install`, or similar commands needed
- NO compilation or transpilation steps
- NO automated tests to run
- NO linting or formatting tools configured
- Simply serve the HTML file via HTTP server and it works

## Validation and Testing

### Manual Validation Requirements
After making ANY changes to `map-creator.html`, ALWAYS perform this complete validation scenario:

1. **Start Server**: `python3 -m http.server 8000`
2. **Open Application**: Navigate to `http://localhost:8000/map-creator.html`
3. **Test Core Workflow**:
   - Click "+ Add Circle Button" - verify numbered circle appears on map
   - Click "+ Add Circle Button" again - verify second numbered circle appears
   - Click on any circle button - verify modal opens with "Room X Media" title
   - In modal, verify "📁 Add Files" button is present and clickable
   - Close modal by clicking "×" button
   - Click "💾 Save Map" button - verify success alert appears
   - Verify circle buttons are draggable on the map
4. **Visual Verification**: Take screenshot to confirm UI renders correctly
5. **Stop Server**: `Ctrl+C` or `pkill -f "python3 -m http.server"`

### Expected Behavior
- Application loads immediately (no loading time)
- Floorplan background shows rooms: Room 1, Room 2, Conference Room, Open Office, Kitchen, Storage, Meeting Room
- Control bar floats at top with blue "Add Circle Button" and green "Save Map" buttons
- Circle buttons are blue with white borders, numbered sequentially
- Modals open smoothly with file upload interface
- Drag and drop of circle buttons works on the map
- **Note**: New circle buttons are created at the same default position (100px, 100px) and may overlap - this is expected behavior

## Key Code Locations

### Main Application File: `map-creator.html`
- **Lines 1-245**: CSS styles for UI components
- **Lines 246-271**: HTML structure (control bar, map container, modal)
- **Lines 272-444**: JavaScript functionality
  - **Lines 277-309**: `addCircleButton()` - Creates new interactive buttons
  - **Lines 311-323**: `openModal()` - Displays media upload interface
  - **Lines 329-364**: `displayMedia()` - Renders uploaded files
  - **Lines 410-435**: File upload handling with base64 conversion
  - **Lines 387-408**: Drag and drop positioning logic

### SVG Floorplan
- **Line 66**: Embedded SVG defines room layout
- Rooms are positioned with specific coordinates
- To modify floorplan: edit the SVG `viewBox` and `<rect>` elements

## Common Development Tasks

### Adding New Features
- Edit `map-creator.html` directly
- Test changes by refreshing browser after serving via HTTP
- All functionality is client-side JavaScript

### Modifying Room Layout
- Edit the SVG background image in line 66
- Adjust `<rect>` coordinates and dimensions for rooms
- Update `<text>` elements for room labels

### Changing Styling
- Modify CSS in the `<style>` section (lines 7-243)
- Use browser dev tools to test changes live
- Key classes: `.control-bar`, `.circle-button`, `.modal`, `.media-gallery`

### Debugging Issues
- Open browser developer tools (F12)
- Check Console tab for JavaScript errors
- Use Network tab to verify file serving (should see 200 status for map-creator.html)
- Inspect Elements tab to verify DOM manipulation

## File Operations and Data Handling
- Files are converted to base64 data URLs and stored in memory
- No server-side storage - all data is client-side only
- File upload supports: images (jpg, png, gif), videos (mp4, webm), documents (pdf, doc, txt)
- Large files may cause performance issues due to base64 encoding

## Troubleshooting

### Common Issues
- **Blank page**: Ensure serving via HTTP server, not opening file directly
- **Buttons not responding**: Check JavaScript console for errors
- **File uploads failing**: Verify browser supports FileReader API
- **Drag and drop not working**: Ensure HTML5 drag events are properly bound

### Browser Compatibility
- Requires modern browser with ES6 support
- Uses HTML5 File API, drag and drop, and CSS Grid
- Tested working in current Chrome, Firefox, Safari

## Development Workflow
1. Make changes to `map-creator.html`
2. Serve via `python3 -m http.server 8000`
3. Test in browser at `http://localhost:8000/map-creator.html`
4. Perform complete validation scenario
5. Take screenshot to verify visual correctness
6. Commit changes

Remember: This is a simple, self-contained application with no complex build pipeline. Focus on direct HTML/CSS/JavaScript editing and manual browser testing.