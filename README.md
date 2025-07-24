# DSDEV Dashboard

A modern, responsive construction site monitoring dashboard for managing security camera feeds, alerts, and site activities. Built with vanilla JavaScript and a custom design system based on the DSDEV brand guidelines.

![DSDEV Dashboard](https://img.shields.io/badge/version-1.0.0-orange.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 🚀 Features

### Camera Management
- **Multi-camera Grid View**: Support for 1x1, 2x2, 3x3, and 4x4 grid layouts
- **Live Streaming**: Start/stop individual or all camera streams
- **Drag & Drop**: Reorder cameras with smooth drag-and-drop functionality
- **Fullscreen Mode**: View any camera feed in fullscreen with dedicated controls
- **Camera Selection**: Add cameras from multiple construction projects
- **Persistent Layout**: Camera arrangement saved to local storage

### Smart Search & Filtering
- **Intelligent Autocomplete**: Search for objects, activities, and events
- **Category-based Results**: Organized by People, Vehicles, Heavy Equipment, Materials, and Activities
- **Real-time Filtering**: Filter cameras by status, project, and alert types

### Alert System
- **Real-time Alerts**: Motion detection, low battery warnings, equipment alerts
- **Alert Panel**: Collapsible side panel with chronological alert feed
- **Visual Indicators**: Badge counts and status indicators

### Fit to Screen Mode
- **Auto-fit Layout**: Dynamically adjusts camera grid to display all feeds without vertical scrolling
- **Smart Grid Selection**: Automatically optimizes grid layout (1x1, 2x2, 3x3, or 4x4) based on camera count
- **Aspect Ratio Preservation**: Maintains 16:9 video aspect ratio with letterboxing/pillarboxing
- **Seamless Integration**: Works with drag-and-drop, adding/removing cameras, and all viewing modes
- **Responsive Degradation**: Automatically disabled on mobile for better touch experience

### Design & Accessibility
- **Dark/Light Mode**: Toggle between themes with persistent preference
- **Fully Responsive**: Optimized for desktop, tablet, and mobile (including iPhone 12)
- **Touch-optimized**: Enhanced controls for mobile devices
- **WCAG Compliant**: Proper contrast ratios and semantic markup
- **Fit to Screen**: Automatically resize all camera feeds to fit within viewport without scrolling

## 🛠️ Technology Stack

- **Frontend**: Vanilla JavaScript (ES6+)
- **Styling**: Custom CSS with CSS Variables
- **Icons**: Custom SVG icon system
- **Fonts**: Manrope (Google Fonts)
- **Build**: No build process required - pure HTML/CSS/JS

## 📋 Requirements

- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
- JavaScript enabled
- Internet connection for video streams and fonts

## 🚀 Getting Started

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/dsdev-dashboard.git
cd dsdev-dashboard
```

2. Open `index.html` in your web browser:
```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

### Development Server (Optional)

For a better development experience, use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (requires http-server)
npx http-server

# Using PHP
php -S localhost:8000
```

## 📖 Usage

### Adding Cameras

1. Click the "Add Camera" card in the grid
2. Select a project from the sidebar
3. Choose available cameras (online cameras only)
4. Click "Add Selected" to add them to your dashboard

### Managing Camera Views

- **Start Stream**: Click the play button on any camera
- **Fullscreen**: Click the expand icon to view in fullscreen
- **Reorder**: Drag and drop camera cards to rearrange
- **Remove**: Hover over a camera and click the × button

### Fit to Screen Mode

1. Click the "Display" button in the header controls
2. Toggle "Fit to Screen" to enable/disable the feature
3. When enabled:
   - All camera feeds resize to fit within your screen
   - No vertical scrolling required
   - Grid layout automatically adjusts based on camera count
   - Video aspect ratios are preserved with black bars as needed
4. The setting persists across page reloads
5. Works best on desktop and tablet displays

**Automatic Grid Optimization:**
- 1 camera: Full screen view
- 2-4 cameras: 2×2 grid
- 5-9 cameras: 3×3 grid
- 10-16 cameras: 4×4 grid

### Search Functionality

The search bar supports intelligent filtering for:
- **People**: Person, Hard Hat, Safety Vest
- **Vehicles**: Car, Pickup Truck, Truck
- **Heavy Equipment**: Bulldozer, Crane, Excavator, etc.
- **Materials**: Scaffolding, Rebar, Traffic Cone, etc.
- **Activities**: Concrete Pour, Excavation, Crane Operation, etc.

### Keyboard Shortcuts

- `Esc` - Exit fullscreen mode
- `Click outside` - Close modals and dropdowns

## 🎨 Design System

The dashboard uses the DSDEV design system with custom design tokens:

### Color Palette

#### Primary Colors
- **DSDEV Orange**: `#f79837` - Primary brand color
- **DSDEV Aqua**: `#00a8ad` - Secondary accent
- **DSDEV Gray**: Neutral scale from `#f9f9f9` to `#333335`

#### Semantic Colors
- **Success**: `#17b26a`
- **Error**: `#f04438`
- **Warning**: `#eaaa08`

### Typography

- **Font Family**: Manrope
- **Weights**: 300, 400, 500, 600, 700
- **Scale**: 12px to 72px with predefined styles

### Spacing System

Based on 4px grid:
- `spacing-1`: 4px
- `spacing-2`: 8px
- `spacing-3`: 12px
- `spacing-4`: 16px
- `spacing-5`: 20px
- `spacing-6`: 24px
- `spacing-8`: 32px
- `spacing-10`: 40px

### Responsive Grid System

The dashboard features an intelligent grid system that adapts to different viewing modes:

- **Standard Mode**: Fixed aspect ratio (16:9) with vertical scrolling
- **Fit to Screen Mode**: Dynamic sizing to eliminate scrolling
- **Adaptive Layouts**: 1×1, 2×2, 3×3, and 4×4 grid configurations
- **Gap Optimization**: Reduced spacing in fit-to-screen mode for maximum viewing area

## 📱 Mobile Support

Fully responsive with specific optimizations for:
- **Desktop**: 1024px and above
- **Tablet**: 768px - 1023px
- **Mobile**: 430px - 767px
- **iPhone 12**: 390px × 844px
- **Small Mobile**: 360px and below

### Mobile Features
- Horizontal scrolling for project selection
- Bottom sheet modal design
- Touch-optimized controls
- Safe area inset support for notched devices

## 🔧 Configuration

### Camera Projects

Projects and cameras are configured in the `projectsData` object:

```javascript
const projectsData = {
  'project-id': {
    name: 'Project Name',
    cameras: [
      {
        id: 'camera-id',
        name: 'Camera Name',
        status: 'online', // online, offline, maintenance
        battery: 85,      // 0-100
        type: 'video'     // video, image
      }
    ]
  }
};
```

### Theme Customization

Modify CSS variables in `:root` or theme-specific selectors:

```css
[data-theme="custom"] {
  --color-orange-500: #your-color;
  --bg-primary: #your-background;
  /* ... other variables */
}
```

### Fit to Screen Configuration

The fit-to-screen feature can be programmatically controlled:

```javascript
// Enable fit-to-screen mode
document.getElementById('fitToScreenToggle').click();

// Check current state
const isFitToScreen = localStorage.getItem('fitToScreen') === 'true';

// Manually adjust grid for fit-to-screen
adjustGridForFitToScreen();
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Style Guidelines

- Use ES6+ features
- Follow existing naming conventions
- Comment complex logic
- Ensure mobile compatibility
- Test in multiple browsers

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
