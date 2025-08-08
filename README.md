# Map Creator

A web-based interactive floorplan editor that allows users to create custom maps with multimedia content. Built as a single HTML file with no dependencies, Map Creator enables users to place interactive buttons on a floorplan and attach media files (images, videos, documents) to specific locations.

![Map Creator Interface](https://github.com/user-attachments/assets/28ecacf5-671a-47e8-9d1d-803129f1a93c)

## Features

### Interactive Floorplan Editor
- **Visual Floorplan**: Pre-designed building layout with labeled rooms (Room 1, Room 2, Conference Room, Open Office, Kitchen, Storage, Meeting Room)
- **Draggable Buttons**: Add numbered circle buttons that can be positioned anywhere on the map
- **Persistent Positioning**: Button locations are maintained throughout the editing session

![Interactive Buttons](https://github.com/user-attachments/assets/9f56dc00-4d73-45cf-bc70-faac919ee027)

### Media Management
- **Multi-format Support**: Upload and attach images, videos, and documents to each button
- **Individual Galleries**: Each button maintains its own collection of media files
- **File Upload Interface**: Simple drag-and-drop or click-to-upload functionality

![Media Upload Modal](https://github.com/user-attachments/assets/842c855b-4f58-417e-9177-ec136d3136e1)

### Export & Save
- **Map Export**: Save the completed map with all button positions and media attachments
- **Base64 Embedding**: Option to inline all media files for self-contained maps
- **Static Output**: Generate maps without editing controls for end-user viewing

## Getting Started

### Prerequisites
- Modern web browser with HTML5 support
- Python 3 (for local development server)

### Installation & Usage

1. **Clone or download** the repository:
   ```bash
   git clone https://github.com/brdominguez/map-creator.git
   cd map-creator
   ```

2. **Start a local HTTP server**:
   ```bash
   python3 -m http.server 8000
   ```

3. **Open the application** in your browser:
   ```
   http://localhost:8000/index.html
   ```

> **Note**: The application must be served via HTTP (not opened directly as a file) to function properly.

## How to Use

1. **Add Buttons**: Click the "+ Add Circle Button" to place numbered buttons on the map
2. **Position Buttons**: Drag buttons to desired locations on the floorplan
3. **Add Media**: Click any button to open its media gallery and upload files
4. **Save Map**: Use the "💾 Save Map" button to export your completed interactive map

## Technical Details

- **Single File Application**: Complete functionality contained in one HTML file (index.html)
- **No Dependencies**: No external libraries, frameworks, or build tools required
- **Client-Side Only**: All processing happens in the browser
- **Modern Web Standards**: Uses HTML5, CSS Grid, ES6 JavaScript
- **File Support**: Images (jpg, png, gif), Videos (mp4, webm), Documents (pdf, doc, txt)
- **Browser Compatibility**: Works in modern browsers with ES6 and File API support

## File Structure
```
map-creator/
├── README.md           # This documentation
├── index.html          # Complete application
└── .github/            # GitHub configuration
```
