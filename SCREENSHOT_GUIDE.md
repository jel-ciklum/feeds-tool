# Screenshot Guide for Feed Testing Tool Mockups

## Required Screenshots

This guide will help you capture all necessary screenshots from the interactive mockup.

---

## Preparation

1. Open `feed-testing-tool-wireframes.html` in Google Chrome or Firefox
2. Set browser window to **1920x1080** for consistency
3. Use full-page screenshot extension or browser DevTools

### Recommended Tools
- **Chrome**: Use DevTools (F12) → Three dots menu → "Capture full size screenshot"
- **Firefox**: Right-click → "Take Screenshot" → "Save full page"
- **Extension**: [Fireshot](https://getfireshot.com/) or [Full Page Screen Capture](https://chrome.google.com/webstore/detail/full-page-screen-capture/fdpohaocaechififmbbbbbknoalclacl)

---

## Screenshot 1: Events List View
**Filename**: `01-events-list.png`

### Steps:
1. Open the mockup HTML file
2. Ensure **"Events List"** tab is active (should be by default)
3. Make sure all filters show "All Sports", "All Statuses", "All Phases"
4. Scroll to show the complete events table (5 events should be visible)
5. Include the Design Notes section at the bottom
6. **Take full-page screenshot**

### What Should Be Visible:
- ✅ Page title and navigation tabs
- ✅ Filter section (Sport, Status, Phase dropdowns + Clear Filters button)
- ✅ "Showing X events" count
- ✅ Complete events table with all 5 events
- ✅ All columns visible (Event ID through Markets)
- ✅ Provider badges on each event
- ✅ Info (ⓘ) and arrow (→) icons
- ✅ Design Notes section at bottom

---

## Screenshot 2: Event Detail - Single Provider Mode
**Filename**: `02-event-detail-single-provider.png`

### Steps:
1. Click **"Event Detail View"** tab
2. Ensure **"Single Provider"** button is active (blue)
3. Make sure **"Optic Odds"** is selected in the provider dropdown
4. Scroll to show all market cards
5. **Take full-page screenshot**

### What Should Be Visible:
- ✅ "Event: Real Madrid vs Manchester City" with LIVE badge
- ✅ "View Mode:" section with "Single Provider" button active
- ✅ Provider dropdown showing "Optic Odds"
- ✅ Event metadata grid (Event ID, Sport, League, Start Time)
- ✅ "Available Markets - Optic Odds" heading
- ✅ All 3 market cards:
  - 1X2 - Match Result (Active)
  - Over/Under 2.5 (Active)
  - First Goalscorer (Active)
- ✅ Design Notes at bottom

### Optional: Capture with different providers
You can also capture:
- `02b-event-detail-single-lsports.png` (Select "LSports" in dropdown)
- `02c-event-detail-single-foxbet.png` (Select "FoxBet" in dropdown)
- `02d-event-detail-single-txodds.png` (Select "TX Odds" in dropdown)

---

## Screenshot 3: Event Detail - Multi-Provider Mode (Compare OFF)
**Filename**: `03-event-detail-multi-provider.png`

### Steps:
1. Stay on **"Event Detail View"** tab
2. Click **"Multi-Provider"** button
3. **Important**: Make sure "Enable Compare Mode" button is **NOT** clicked (should be in default state)
4. Scroll to show both provider panels completely
5. **Take full-page screenshot**

### What Should Be Visible:
- ✅ "Multi-Provider" button active (blue)
- ✅ "Enable Compare Mode" button visible (not orange)
- ✅ "Side-by-Side Comparison View" section
- ✅ Compare Mode explanation bullets (NOT the orange notice)
- ✅ Left panel: "Optic Odds" with 4 markets
  - 1X2 • Match Result (NO orange highlights)
  - Over/Under • Total Goals 2.5 (NO orange highlights)
  - Both Teams to Score
  - Total Corners Over/Under 10.5
- ✅ Right panel: "LSports" with 5 markets
  - 1X2 • Match Winner (NO orange highlights)
  - Over/Under • Over/Under 2.5 Goals (NO orange highlights)
  - Asian Handicap -0.5
  - Double Chance
  - Halftime/Fulltime
- ✅ No orange borders or highlights visible
- ✅ Design Notes at bottom

---

## Screenshot 4: Event Detail - Compare Mode ACTIVE
**Filename**: `04-event-detail-compare-mode.png`

### Steps:
1. Stay on **"Event Detail View"** tab with "Multi-Provider" active
2. Click **"Enable Compare Mode"** button
3. **Wait for highlights to appear** (should be immediate)
4. Scroll to show both provider panels with all highlights visible
5. **Take full-page screenshot**

### What Should Be Visible:
- ✅ "Disable Compare Mode" button (orange background)
- ✅ **Optic Odds panel** (LEFT):
  - 🟠 Orange border on 1X2 card
  - 🟠 Orange border on Over/Under card
  - 🟠 "Match Result" with orange "⚠️ Name Diff" tag
  - 🟠 All odds highlighted in orange (Home, Draw, Away)
  - 🟠 "Total Goals 2.5" with orange "⚠️ Name Diff" tag
  - 🟠 Over/Under odds highlighted in orange
- ✅ **LSports panel** (RIGHT):
  - 🟠 Orange border on 1X2 card
  - 🟠 Orange border on Over/Under card
  - 🟠 "Match Winner" with orange "⚠️ Name Diff" tag
  - 🟠 All odds highlighted in orange (Home, Draw, Away)
  - 🟠 "Over/Under 2.5 Goals" with orange "⚠️ Name Diff" tag
  - 🟠 Over/Under odds highlighted in orange
- ✅ Orange notice at bottom explaining differences
- ✅ Design Notes at bottom

---

## Screenshot 5: Market Detail Side Panel
**Filename**: `05-market-detail-side-panel.png`

### Steps:
1. Go to **"Market Detail & Messages"** tab
2. This shows the side panel layout as it would appear
3. Scroll to show all sections
4. **Take full-page screenshot**

### What Should Be Visible:
- ✅ "Screen 3: Market Detail & Message Inspection (Side Panel)" title
- ✅ Side panel mockup (800px width appearance)
- ✅ Panel header with market name and close button
- ✅ All content sections:
  - 📊 Market Summary (yellow highlights)
  - 🔄 Applied Mappings (purple highlights with rule IDs)
  - 📥 Provider Message (Raw) - JSON with copy button
  - 📤 Transformed Message (Output) - JSON with copy button
- ✅ Syntax-highlighted JSON
- ✅ Copy buttons on both JSON sections
- ✅ Design Notes at bottom

---

## Screenshot 6 (Optional): Side Panel in Action
**Filename**: `06-side-panel-open.png`

This requires a browser screenshot tool that captures overlays. This is **optional** but nice to have.

### Steps:
1. Go to "Event Detail View" tab
2. Click on any market card
3. **Immediately** take screenshot to capture the alert/mockup
4. OR: Use browser DevTools to manually trigger the side panel appearance

**Note**: Since the side panel is currently showing as alerts, this screenshot may not work perfectly. This is why we have Screenshot 5 showing the panel layout.

---

## Batch Screenshot Script (Optional)

If you want to automate screenshots using Puppeteer or similar:

```javascript
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.setViewport({ width: 1920, height: 1080 });
  
  await page.goto('file:///path/to/feed-testing-tool-wireframes.html');
  
  // Screenshot 1: Events List
  await page.click('[data-screen="events-list"]');
  await page.screenshot({ path: '01-events-list.png', fullPage: true });
  
  // Screenshot 2: Single Provider
  await page.click('[data-screen="event-detail-multi"]');
  await page.click('#single-provider-btn');
  await page.screenshot({ path: '02-event-detail-single-provider.png', fullPage: true });
  
  // Screenshot 3: Multi-Provider (Compare OFF)
  await page.click('#multi-provider-btn');
  await page.screenshot({ path: '03-event-detail-multi-provider.png', fullPage: true });
  
  // Screenshot 4: Compare Mode Active
  await page.click('#compare-mode-btn-merged');
  await page.waitForTimeout(500);
  await page.screenshot({ path: '04-event-detail-compare-mode.png', fullPage: true });
  
  // Screenshot 5: Side Panel
  await page.click('[data-screen="market-detail"]');
  await page.screenshot({ path: '05-market-detail-side-panel.png', fullPage: true });
  
  await browser.close();
})();
```

---

## Quality Checklist

Before finalizing screenshots:

- [ ] All screenshots are **1920px wide** (or consistent width)
- [ ] Text is **crisp and readable**
- [ ] Colors are **accurate** (not washed out)
- [ ] **No browser UI** visible (address bar, bookmarks, etc.)
- [ ] **Complete content** visible (no cut-off sections)
- [ ] File names match the convention exactly
- [ ] Files are saved as **PNG** (not JPG)
- [ ] File sizes are reasonable (< 500KB per image if possible)

---

## After Taking Screenshots

1. Review all images to ensure quality
2. Place in `/docs/mockups/feed-testing-tool/` directory
3. Verify file names match README references
4. Commit to Git with descriptive message
5. Update PRD/User Stories with links to mockups

---

## Troubleshooting

**Problem**: Screenshots are blurry
- **Solution**: Increase browser zoom to 100%, use higher resolution monitor

**Problem**: Side panel doesn't capture properly
- **Solution**: Use Screenshot 5 (the dedicated screen) instead of trying to capture the overlay

**Problem**: Colors look different in screenshots
- **Solution**: Use same browser for all screenshots, check monitor color calibration

**Problem**: Content is cut off
- **Solution**: Use "full page screenshot" option, not viewport screenshot

---

## Need Help?
If you have issues capturing screenshots, you can also:
1. Share the HTML file with a designer
2. Use online screenshot services like [Screenshot.guru](https://screenshot.guru)
3. Record a screen video and extract frames
