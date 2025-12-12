# MBTA Route 426 Tracker - PWA

A Progressive Web App for real-time tracking of MBTA Route 426 bus with live predictions, interactive map, and offline support.

## 🚀 Features

- **Real-time Bus Tracking**: Live bus locations and arrival predictions
- **Interactive Map**: View route, stops, and bus positions on Leaflet map
- **Visual Progress Bar**: See exactly how many stops away the bus is from your location
- **Offline Support**: Service worker caches app for offline use
- **PWA Installable**: Add to home screen on iOS and Android
- **Weather Integration**: Current weather conditions
- **iOS & Android Optimized**: Touch gestures, safe areas, and native feel

## 📱 Installation

### For iOS (Safari):
1. Open the app in Safari
2. Tap the Share button (square with arrow)
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add" in the top right

### For Android (Chrome):
1. Open the app in Chrome
2. Tap the menu (three dots)
3. Tap "Add to Home screen" or "Install app"
4. Tap "Install"

## 🛠️ Local Development

### Option 1: Python HTTP Server
```bash
cd "G:\My Drive\Bus to Work - project\Live working"
python -m http.server 8000
```
Then open: http://localhost:8000

### Option 2: VS Code Live Server
1. Install "Live Server" extension in VS Code
2. Right-click on `index.html`
3. Select "Open with Live Server"

### Option 3: Node.js http-server
```bash
npx http-server "G:\My Drive\Bus to Work - project\Live working" -p 8000
```

## 📦 GitHub Pages Deployment

### Step 1: Create GitHub Repository
```bash
cd "G:\My Drive\Bus to Work - project\Live working"
git init
git add .
git commit -m "Initial commit - MBTA 426 Tracker PWA"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/mbta-426-tracker.git
git push -u origin main
```

### Step 2: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click "Settings" → "Pages"
3. Under "Source", select "main" branch
4. Click "Save"
5. Your app will be live at: `https://YOUR_USERNAME.github.io/mbta-426-tracker/`

### Step 3: Update manifest.json (if needed)
If deploying to a subdirectory, update the `start_url` in `manifest.json`:
```json
"start_url": "/mbta-426-tracker/index.html"
```

## 🎨 Creating App Icons

You need to create two icon files:
- `icon-192.png` (192x192 pixels)
- `icon-512.png` (512x512 pixels)

### Quick Icon Generation:
1. **Use an online tool**: https://realfavicongenerator.net/
2. **Or use this simple design**:
   - Blue gradient background (#1a73e8 to #4285f4)
   - White bus emoji 🚌 or "426" text
   - Export as PNG at 512x512, then resize to 192x192

### Using Photoshop/GIMP/Figma:
1. Create 512x512 canvas
2. Add blue gradient background
3. Add white "426" text (bold, centered)
4. Add bus icon if desired
5. Export as PNG
6. Resize to 192x192 for smaller icon

## 📁 File Structure

```
Live working/
├── index.html              # Main app file (copy of mbta-426-tracker-5.html)
├── mbta-426-tracker-5.html # Original development file
├── manifest.json           # PWA manifest
├── sw.js                   # Service worker for offline support
├── icon-192.png           # App icon 192x192 (you need to create)
├── icon-512.png           # App icon 512x512 (you need to create)
└── README.md              # This file
```

## 🔧 Configuration

### Update Your Home Location
Edit `CONFIG` in `index.html`:
```javascript
const CONFIG = {
    YOUR_HOME: { lat: 42.461776, lng: -70.987476 }, // Your coordinates
    // ... other config
};
```

### Update Home Stop IDs
```javascript
ROUTE_INFO: {
    to_haymarket: { 
        homeStopId: '16669',  // Your stop ID going to Haymarket
        homeStopName: 'Boston St @ Winnepurkit Ave'
    },
    to_home: { 
        homeStopId: '7445',   // Your stop ID going home
        homeStopName: 'Boston St @ Browns Ave'
    }
}
```

## 🌐 API Information

This app uses:
- **MBTA V3 API**: Real-time bus data (free, no registration required)
- **Open-Meteo API**: Weather data (free, no API key needed)
- **Leaflet + CartoDB**: Map tiles (free, open source)

## 🐛 Troubleshooting

### CORS Errors
- **Problem**: "Failed to fetch" or CORS errors
- **Solution**: Must serve via HTTP/HTTPS, not file:// protocol
- Use one of the local development options above

### Service Worker Not Registering
- **Problem**: PWA features not working
- **Solution**: Service workers require HTTPS (or localhost)
- GitHub Pages automatically provides HTTPS

### Icons Not Showing
- **Problem**: Default icons appear instead of custom icons
- **Solution**: Create `icon-192.png` and `icon-512.png` files
- Place them in the same directory as `index.html`

### iOS Not Showing Install Prompt
- **Problem**: No "Add to Home Screen" option
- **Solution**: iOS doesn't show automatic prompts
- Manually add via Share button → Add to Home Screen

## 📱 Browser Support

- ✅ iOS Safari 11.3+
- ✅ Android Chrome 40+
- ✅ Desktop Chrome, Firefox, Edge
- ⚠️ IE11 not supported

## 🔒 Privacy

- All data fetched directly from MBTA API
- No user data collected or stored
- No analytics or tracking
- Runs entirely client-side

## 📄 License

MIT License - Feel free to modify and use for your own routes!

## 🤝 Contributing

To adapt this for other MBTA routes:
1. Change `selectedRoute` to your route number
2. Update stop arrays with your route's stops
3. Update home coordinates and stop IDs
4. Modify colors/branding as desired

## 📞 Support

For MBTA API issues: https://www.mbta.com/developers/v3-api
For app issues: Check browser console for error messages

---

**Made with ❤️ for MBTA Route 426 riders**
