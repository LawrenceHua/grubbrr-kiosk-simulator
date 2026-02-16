# GRUBBRR Kiosk Bug Simulator

Interactive kiosk simulator for visualizing and documenting bug fixes in the GRUBBRR self-service kiosk system.

## Overview

This simulator provides a side-by-side view of the GRUBBRR kiosk interface and bug documentation, allowing developers and QA to:

- Toggle between **BROKEN** and **FIXED** states
- Click bugs to highlight affected UI elements
- View detailed bug information (JIRA ID, description, fix, test status)
- Navigate through different kiosk screens

## Features

- **Real-time Bug Highlighting**: Click any bug in the sidebar to see exactly where it manifests in the UI
- **State Toggle**: Switch between broken and fixed states to compare before/after
- **Screen Navigation**: Payment, Refund, Scanner, Order screens
- **JIRA Integration**: All bugs linked to actual NGE tickets

## File Structure

```
grubbrr-kiosk-simulator/
├── index.html          # Main simulator (single file, no dependencies)
├── README.md           # This file
├── BUGS.md            # Detailed bug documentation
└── CHANGELOG.md       # Version history
```

## Usage

### Local Development

```bash
# Serve locally (any static server works)
python3 -m http.server 8000
# or
npx serve .
# or simply open index.html in browser
```

### Deployed Version

https://grubbrr-kiosk-simulator.netlify.app

## Bug Documentation

All bugs are documented with:
- **JIRA ID**: NGE-XXXXX
- **Priority**: Highest, High, Medium
- **Category**: payment, ui, api, state
- **Screen**: Which kiosk screen affected
- **Business Impact**: Why it matters
- **Fix Applied**: Technical solution
- **Test Status**: Number of tests passing

## Screens

### Payment Screen
- Card type display
- Payment method selection
- Related bugs: NGE-13870

### Refund Screen
- Refund status display
- Order history
- Related bugs: NGE-13857

### Scanner Screen
- QR code scanner
- Loyalty card scanning
- Related bugs: NGE-13820

### Order Screen
- Quantity controls
- Item management
- Related bugs: NGE-13897

## Development

### Adding New Bugs

Edit the `bugs` array in `index.html`:

```javascript
const bugs = [
  {
    id: 'NGE-XXXXX',
    title: 'Bug description',
    priority: 'Highest',
    category: 'payment',
    screen: 'payment',
    selector: '#element-id',
    impact: 'Business impact description',
    fix: 'Technical fix applied',
    tests: 'X tests passing',
    fixed: true
  }
];
```

### Adding New Screens

1. Add HTML panel in `.kiosk-content`
2. Add nav button in `.kiosk-nav`
3. Update `switchScreen()` function

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Team

- **Product**: GRUBBRR Engineering
- **JIRA Project**: NGE (Next Gen Engineering)
- **Repo**: https://github.com/LawrenceHua/grubbrr-kiosk-simulator

## License

Internal Use Only - GRUBBRR
