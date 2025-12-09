# Feed Integration Testing & Demo Tool - Mockups

## Overview
Interactive mockups for the Feed Integration Testing & Demo Tool, designed for developers and QAs to manually test betting feed integrations and perform demo presentations.

## Purpose
This tool enables testing and validation of feed integrations from multiple providers (Optic Odds, LSports, FoxBet, TX Odds) by displaying betting markets with real-time feed updates and provider comparison capabilities.

---

## Screens Overview

### Screen 1: Events List View
**File**: `01-events-list.png` | **Interactive**: Open `feed-testing-tool-wireframes.html` → "Events List" tab

**Purpose**: Primary landing page displaying all events/fixtures received from feed providers in real-time.

**Key Features**:
- Filterable event table (Sport, Status, Phase)
- Real-time event count updates
- Provider badges showing all providers offering each event
- Dual navigation:
  - **Info icon (ⓘ)**: Opens detail view side panel without navigation
  - **Arrow icon (→)**: Navigates to multi-provider event detail view

**Columns**:
- Event ID
- Sport
- Class
- League
- Teams
- Start Time
- Status (Active/Closed/Suspended)
- Phase (Pre-match/In-play/Post-match)
- Providers (badges)
- Markets (count)

---

### Screen 2: Event Detail View - Single Provider Mode
**File**: `02-event-detail-single-provider.png`

**Purpose**: Shows detailed markets from one selected provider with real-time updates.

**Key Features**:
- Provider selector dropdown (Optic Odds, LSports, FoxBet, TX Odds)
- Market status badges (Active, Suspended, Closed, Resulted)
- Result indicators (Win/Lose/Void) on completed markets
- Click any market card to open side panel with detailed messages
- Dynamic market updates when switching providers

**Market Types by Provider**:
- **Optic Odds**: 1X2, Over/Under, First Goalscorer
- **LSports**: 1X2, Over/Under, Both Teams to Score
- **FoxBet**: 1X2, Over/Under (common markets only)
- **TX Odds**: 1X2, Over/Under, Correct Score

---

### Screen 2: Event Detail View - Multi-Provider Comparison
**File**: `03-event-detail-multi-provider.png`

**Purpose**: Side-by-side comparison of the same event across multiple providers.

**Key Features**:
- Side-by-side view of Optic Odds and LSports
- Internal market names (1X2, Over/Under) with provider-specific display names
- Market count badges per provider
- Compare Mode button (disabled by default)
- Real-time updates on both sides

**Display Format**:
- Internal Name • Provider-Specific Name
- Example: `1X2 • Match Result` (Optic Odds) vs `1X2 • Match Winner` (LSports)

---

### Screen 2: Event Detail View - Compare Mode Active
**File**: `04-event-detail-compare-mode.png`

**Purpose**: Highlights all differences between providers for validation and mapping verification.

**Compare Mode Highlights** (when enabled):
- 🟠 **Orange borders** on cards with differences
- 🟠 **Provider name differences**: "Match Result" vs "Match Winner"
- 🟠 **All odds differences** highlighted in orange:
  - 1X2: Home (2.10 vs 2.15), Draw (3.50 vs 3.45), Away (3.20 vs 3.10)
  - Over/Under: Over (1.85 vs 1.90), Under (1.95 vs 1.90)
- ⚠️ **Name Diff warnings** on provider-specific names
- 📊 **Explanatory notice** detailing all differences

**Toggle Behavior**:
- Click "Enable Compare Mode": Highlights appear
- Click "Disable Compare Mode": Clean comparison view returns

---

### Screen 3: Market Detail & Message Inspection (Side Panel)
**File**: `05-market-detail-side-panel.png`

**Purpose**: Displayed in 800px side panel when clicking market cards or event info icons.

**Content Sections**:

1. **📊 Market Summary** (yellow highlights)
   - Market type, status, last updated
   - Current selections and odds

2. **🔄 Applied Mappings** (purple highlights)
   - Market type mappings (e.g., "match_winner" → "1X2")
   - Outcome name mappings (e.g., "home" → "Home Win")
   - Team name mappings
   - Rule IDs shown in purple code tags

3. **📥 Provider Message (Raw)**
   - Full JSON with syntax highlighting
   - Copy button for clipboard

4. **📤 Transformed Message (Output)**
   - Standardized JSON with syntax highlighting
   - Shows all transformations applied
   - Copy button for clipboard

**Interaction**:
- Opens from right side of screen
- Click X to close
- All JSON sections have working copy buttons
- Scrollable content

---

## Technical Specifications

### Providers
- **Optic Odds**: 3 markets (1X2, Over/Under, First Goalscorer)
- **LSports**: 3 markets (1X2, Over/Under, Both Teams to Score)
- **FoxBet**: 2 markets (1X2, Over/Under only)
- **TX Odds**: 3 markets (1X2, Over/Under, Correct Score)

### Market Naming Convention
**Format**: `Internal Name • Provider-Specific Display Name`

**Examples**:
- Optic Odds: `1X2 • Match Result`
- LSports: `1X2 • Match Winner`
- Optic Odds: `Over/Under • Total Goals 2.5`
- LSports: `Over/Under • Over/Under 2.5 Goals`

### Status Badges
- **Active** (green): Market accepting bets
- **Suspended** (yellow): Temporarily unavailable
- **Closed** (gray): No longer accepting bets
- **Resulted** (gray): Final outcome determined

### Phase Badges
- **Pre-match** (blue): Before event starts
- **In-play** (green): Event currently happening
- **Post-match** (gray): Event completed

---

## Usage Instructions

### For Developers & QAs

**Testing Workflow**:
1. Start on **Screen 1** (Events List)
2. Filter by Sport/Status/Phase to find target event
3. Click **→ arrow icon** to navigate to event details
4. Select **Single Provider mode** to test one provider's markets
5. Switch to **Multi-Provider mode** to compare providers
6. Enable **Compare Mode** to validate mappings and identify discrepancies
7. Click any **market card** to inspect raw/transformed messages

**Side Panel Inspection**:
- Click **ⓘ info icon** on events list for quick event inspection
- Click any **market card** for detailed market messages
- Use **copy buttons** to extract JSON for testing/debugging

### For Demos

**Demonstration Flow**:
1. Show **Events List** with real-time updates and provider coverage
2. Navigate to **Multi-Provider view** showing side-by-side comparison
3. Enable **Compare Mode** to highlight provider differences
4. Open **Side Panel** to show raw provider data and transformations
5. Emphasize mapping accuracy and real-time synchronization

---

## Interactive HTML Features

The `feed-testing-tool-wireframes.html` file includes:

### Working Features
✅ Tab navigation between screens
✅ Functional filters (Sport, Status, Phase)
✅ Dynamic event count updates
✅ Provider selector with dynamic market updates
✅ Single/Multi-Provider mode toggle
✅ Compare Mode enable/disable with live highlighting
✅ Side panel open/close functionality
✅ JSON copy-to-clipboard buttons with success feedback

### Mock Interactions
⚠️ Data is static/mock (not connected to real feeds)
⚠️ Clicking events/markets shows example data
⚠️ Real-time updates are simulated with static timestamps

---

## File Structure

```
/docs/mockups/feed-testing-tool/
├── README.md                                    # This file
├── feed-testing-tool-wireframes.html           # Interactive mockup
├── 01-events-list.png                          # Screen 1 screenshot
├── 02-event-detail-single-provider.png         # Screen 2 (Single mode)
├── 03-event-detail-multi-provider.png          # Screen 2 (Multi mode)
├── 04-event-detail-compare-mode.png            # Screen 2 (Compare active)
└── 05-market-detail-side-panel.png             # Screen 3 (Side panel)
```

---

## Integration with Requirements

### PRD References
These mockups support the following PRD sections:
- **Provider Integration**: Visual representation of multi-provider data ingestion
- **Mapping & Instances**: Shows internal name standardization and provider-specific mappings
- **Feed Aggregation**: Demonstrates real-time multi-provider comparison
- **Provider Health Monitoring**: Status badges and real-time update indicators

### User Stories
Mockups map to user stories for:
- **Feed Testing**: Manual validation of provider feeds
- **Provider Comparison**: Side-by-side market comparison
- **Mapping Validation**: Compare mode highlighting of discrepancies
- **Demo Presentations**: Stakeholder-friendly visualization

---

## Design Decisions

### Why Side-by-Side Comparison?
Shows market differences visually, making it easy to spot naming inconsistencies, odds variations, and missing markets across providers.

### Why Compare Mode Toggle?
Allows QAs to switch between clean comparison (for normal testing) and highlighted differences (for validation/debugging) without overwhelming the interface.

### Why Side Panel for Messages?
Keeps users in context while inspecting technical details. Avoids navigation away from the comparison view.

### Why Internal + Provider Names?
Makes it immediately clear which markets map together despite different provider naming conventions. Critical for validation.

---

## Next Steps

### For Screenshots
1. Open `feed-testing-tool-wireframes.html` in browser
2. Navigate to each screen/state
3. Take full-page screenshots
4. Save as PNG with provided naming convention

### For Git Repository
```bash
# Create mockups directory
mkdir -p docs/mockups/feed-testing-tool

# Copy files
cp feed-testing-tool-wireframes.html docs/mockups/feed-testing-tool/
cp *.png docs/mockups/feed-testing-tool/
cp README.md docs/mockups/feed-testing-tool/

# Commit and push
git add docs/mockups/feed-testing-tool/
git commit -m "Add Feed Integration Testing Tool mockups"
git push origin <branch-name>
```

### Reference in PRD
Add to PRD document:
```markdown
## Visual Design
Interactive mockups and screenshots available at:
`/docs/mockups/feed-testing-tool/README.md`

View interactive version: `/docs/mockups/feed-testing-tool/feed-testing-tool-wireframes.html`
```

---

## Questions or Issues?
Contact: Product Management (Feeds Domain)
Last Updated: December 2025
