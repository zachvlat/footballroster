# Football Roster Builder - Specification

## 1. Project Overview
- **Project name**: Football Roster Builder
- **Type**: Single-page web application (HTML/CSS/JS)
- **Core functionality**: Create and manage football rosters by searching real players via API or adding custom players
- **Target users**: Football enthusiasts, coaches, fantasy team builders

## 2. UI/UX Specification

### Layout Structure
- **Header**: App title, theme toggle button
- **Main area**: 
  - Search panel (left sidebar on desktop, top on mobile)
  - Roster display (right/main area)
- **Responsive breakpoints**:
  - Mobile: < 768px (stacked layout)
  - Desktop: >= 768px (side-by-side)

### Visual Design

#### Color Palette
**Light Mode**:
- Background: `#f5f5f0`
- Card/Surface: `#ffffff`
- Primary: `#1a5f2a` (grass green)
- Secondary: `#2d4a35`
- Accent: `#d4af37` (gold)
- Text primary: `#1a1a1a`
- Text secondary: `#5a5a5a`
- Border: `#e0e0e0`

**Dark Mode**:
- Background: `#121212`
- Card/Surface: `#1e1e1e`
- Primary: `#3d8b40`
- Secondary: `#5a7d5a`
- Accent: `#f0c850`
- Text primary: `#f0f0f0`
- Text secondary: `#a0a0a0`
- Border: `#333333`

#### Typography
- **Font family**: `'Outfit', sans-serif` (Google Fonts)
- **Headings**: 700 weight
- **Body**: 400 weight
- **Sizes**: 
  - H1: 2rem
  - H2: 1.5rem
  - Body: 1rem
  - Small: 0.875rem

#### Spacing
- Base unit: 8px
- Card padding: 16px
- Section gaps: 24px
- Border radius: 12px

### Components

#### Theme Toggle
- Icon button (sun/moon)
- Smooth transition between modes

#### Search Panel
- Input field with search icon
- Results dropdown list
- Each result shows: player image, name, position, rating, club
- "Add as custom player" option if no results

#### Roster Display
- Grid of player cards (3 columns on desktop, 2 on mobile)
- Each card shows:
  - Player image (or placeholder)
  - Name
  - Position
  - Rating (gold badge)
  - Club
  - Remove button
- Empty slot placeholders

#### Player Card
- Rounded corners
- Subtle shadow
- Hover: slight lift effect
- Remove button (X) on hover

#### Add Custom Player Modal
- Form fields: Name, Position, Rating, Club, Nationality
- Save and Cancel buttons

## 3. Functionality Specification

### Core Features
1. **Player Search**
   - Real-time search as user types (debounced 300ms)
   - Call API: `https://api.lineup-builder.co.uk/api/26/player?name={name}&limit=7&skip=0&showIcons=true`
   - Display up to 7 results
   - Show player image, name, positions, rating, club

2. **Add Player to Roster**
   - Click on search result to add to roster
   - Maximum 11 players in roster
   - Show warning when roster is full

3. **Remove Player**
   - Click X button on player card
   - Remove from roster

4. **Custom Player Addition**
   - If API returns no players, show "Add custom player" option
   - Opens modal form
   - Fields: Name (required), Position (dropdown), Rating (1-99), Club, Nationality
   - Name is auto-capitalized (first letter uppercase)

5. **Theme Toggle**
   - Persist preference in localStorage
   - Smooth CSS transition

### Data Handling
- Store roster in localStorage
- Load roster on page load
- Update localStorage on any change

### Edge Cases
- API error: show "Unable to search players" message
- Empty search: clear results
- Duplicate player: allow (same player can be added twice)
- Roster full: disable adding, show message

## 4. Acceptance Criteria
- [ ] Theme toggle works and persists
- [ ] Search returns results from API
- [ ] No results shows custom player option
- [ ] Custom player form capitalizes name
- [ ] Players can be added to roster
- [ ] Players can be removed from roster
- [ ] Roster persists after page refresh
- [ ] Responsive on mobile and desktop