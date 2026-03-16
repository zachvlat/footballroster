# Football Roster Builder

A desktop application to build and manage football rosters by searching real players via API or adding custom players. Drag & drop players onto a tactical pitch.

## Features

- Search real players via Fotmob API
- Drag & drop onto a vertical 5x3 tactical pitch
- Roster panel with position groups (GK, Defenders, Midfielders, Attackers)
- Add custom players
- Light/dark theme toggle
- Import/Export roster as JSON
- LocalStorage persistence

## Development

```bash
# Install dependencies
npm install

# Run in development mode
npm start
```

## Building

```bash
# Build for current platform
npm run build

# Build for specific platforms
npm run build:win    # Windows (.exe installer)
npm run build:mac    # macOS (.dmg)
npm run build:linux  # Linux (.AppImage)
```

Builds are generated in the `dist/` folder.

## Linux Flatpak Build

For Flatpak, you need [flatpak-builder](https://flatpak.org/) installed:

```bash
# Create the flatpak build directory and manifest
flatpak-builder --force-clean build-dir flatpak/com.footballroster.app.yml

# Build the flatpak
flatpak build-bundle dist/ football-roster.flatpak com.footballroster.app
```

## License

ISC