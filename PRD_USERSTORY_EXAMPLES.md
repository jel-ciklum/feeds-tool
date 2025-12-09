# Integration Examples - PRD & User Stories

This document provides copy-paste examples for referencing the mockups in your Product Requirements Documents (PRDs) and User Stories.

---

## 🎯 PRD Integration Examples

### Example 1: Full PRD Section

```markdown
## Visual Design & User Interface

### Mockups & Wireframes
Complete interactive mockups for the Feed Integration Testing & Demo Tool are available at:
- **Documentation**: `/docs/mockups/feed-testing-tool/README.md`
- **Interactive Mockup**: `/docs/mockups/feed-testing-tool/feed-testing-tool-wireframes.html`

### Screen Overview

#### Screen 1: Events List View
Primary landing page displaying all events from feed providers with real-time updates.
- **Screenshot**: `01-events-list.png`
- **Features**: Filterable table, provider badges, dual navigation (info panel / event detail)

#### Screen 2: Event Detail View
Unified view with toggle between Single Provider and Multi-Provider modes.
- **Screenshots**: 
  - `02-event-detail-single-provider.png` (Single mode)
  - `03-event-detail-multi-provider.png` (Multi mode)
  - `04-event-detail-compare-mode.png` (Compare mode active)
- **Features**: Provider selector, market cards, side-by-side comparison, difference highlighting

#### Screen 3: Market Detail & Message Inspection
Side panel (800px) displaying raw messages, transformations, and mappings.
- **Screenshot**: `05-market-detail-side-panel.png`
- **Features**: JSON inspection, copy buttons, mapping visualization

### Design Principles
See mockup README for detailed design decisions and rationale.
```

---

### Example 2: Compact PRD Reference

```markdown
## User Interface Design

Visual mockups available: `/docs/mockups/feed-testing-tool/`

**Key Screens**:
1. Events List - Filterable event table with provider visibility
2. Event Detail - Single/Multi-provider toggle with compare mode
3. Market Detail - Side panel with message inspection

Interactive demo: `feed-testing-tool-wireframes.html`
```

---

### Example 3: Technical Specification Section

```markdown
## Component: Feed Testing Tool UI

### Visual Reference
- Mockup Location: `/docs/mockups/feed-testing-tool/`
- Interactive Prototype: `feed-testing-tool-wireframes.html`

### UI Components Required

| Component | Screen | Description | Reference |
|-----------|--------|-------------|-----------|
| Event Table | 1 | Filterable data grid with provider badges | `01-events-list.png` |
| Provider Selector | 2 | Dropdown with dynamic market updates | `02-event-detail-single-provider.png` |
| Compare Toggle | 2 | Button to enable difference highlighting | `04-event-detail-compare-mode.png` |
| Side Panel | 3 | 800px overlay with JSON inspection | `05-market-detail-side-panel.png` |

### Interaction Patterns
- See interactive mockup for click behavior
- Compare mode highlights: Orange borders + badges
- Side panel: Slides from right, 800px width
```

---

## 📋 User Story Integration Examples

### Example 1: Full User Story with Mockup References

```markdown
## User Story: View Multi-Provider Market Comparison

**As a** QA Engineer  
**I want to** compare the same market across multiple providers side-by-side  
**So that** I can validate mapping accuracy and identify discrepancies

### Acceptance Criteria

#### Display & Layout
- [ ] Shows side-by-side panels for two providers (Optic Odds & LSports)
- [ ] Each panel displays provider name and market count badge
- [ ] Markets show internal name (1X2, Over/Under) + provider-specific name
- [ ] Layout matches mockup: `03-event-detail-multi-provider.png`

#### Compare Mode Functionality
- [ ] "Enable Compare Mode" button visible at top right
- [ ] When clicked, button changes to "Disable Compare Mode" (orange)
- [ ] All differences highlighted with orange borders and backgrounds:
  - Provider name variations (e.g., "Match Result" vs "Match Winner")
  - All odds differences (Home, Draw, Away for 1X2; Over, Under for O/U)
- [ ] Explanatory notice appears at bottom showing detected differences
- [ ] Behavior matches mockup: `04-event-detail-compare-mode.png`

#### When Compare Mode Disabled
- [ ] Clean comparison view with no highlighting
- [ ] Markets display normally without orange indicators
- [ ] View matches mockup: `03-event-detail-multi-provider.png`

### Mockup Reference
**Location**: `/docs/mockups/feed-testing-tool/`  
**Interactive**: `feed-testing-tool-wireframes.html` → Event Detail View → Multi-Provider

### Technical Notes
- Real-time updates required on both panels
- Highlighting should be dynamic (client-side)
- Compare logic must check: odds variations, name differences, missing markets
```

---

### Example 2: Simple User Story Format

```markdown
## User Story: Filter Events by Sport

**As a** Developer  
**I want to** filter the events list by sport  
**So that** I can quickly find relevant events for testing

### Acceptance Criteria
- [ ] Sport dropdown shows: All Sports, Soccer, Basketball, American Football, Baseball
- [ ] Selecting a sport filters the table in real-time
- [ ] Event count updates dynamically (e.g., "Showing 2 events")
- [ ] UI matches mockup: `01-events-list.png`

**Mockup**: `/docs/mockups/feed-testing-tool/01-events-list.png`
```

---

### Example 3: Technical Task with Mockup

```markdown
## Task: Implement Side Panel Component

### Description
Build a reusable side panel component (800px width) that displays market details with syntax-highlighted JSON and copy functionality.

### Requirements
- Slides in from right side of screen
- Fixed 800px width
- Sections: Summary, Mappings, Raw JSON, Transformed JSON
- Copy buttons on all JSON blocks
- Close button (X) in header

### Visual Reference
**Mockup**: `05-market-detail-side-panel.png`  
**Location**: `/docs/mockups/feed-testing-tool/`

### Design Specs from Mockup
- Width: 800px
- Background: White (#FFFFFF)
- Shadow: Large drop shadow for overlay effect
- Sections: Yellow highlights (Summary), Purple highlights (Mappings)
- Typography: Manrope (UI), JetBrains Mono (code)

### Behavior
- See interactive mockup for open/close animation
- Must be reusable for both event info and market details
```

---

## 📊 Confluence Page Template

```markdown
# Feed Integration Testing Tool - Design Documentation

## Overview
The Feed Integration Testing & Demo Tool is designed for manual testing of feed integrations from multiple providers.

## Mockups & Prototypes

### Interactive Mockup
📎 [feed-testing-tool-wireframes.html](/docs/mockups/feed-testing-tool/feed-testing-tool-wireframes.html)

### Documentation
📖 [Complete README](/docs/mockups/feed-testing-tool/README.md)

## Screen Designs

### Screen 1: Events List View
![Events List](01-events-list.png)

**Purpose**: Primary landing page for viewing all events

**Key Features**:
- Real-time event updates
- Filterable by Sport, Status, Phase
- Provider visibility badges
- Dual navigation (info icon / arrow icon)

---

### Screen 2: Event Detail View (Single Provider)
![Single Provider](02-event-detail-single-provider.png)

**Purpose**: Focused view of one provider's markets

**Key Features**:
- Provider selector dropdown
- Market status badges
- Result indicators (Win/Lose/Void)
- Dynamic market updates per provider

---

### Screen 2: Event Detail View (Multi-Provider)
![Multi-Provider](03-event-detail-multi-provider.png)

**Purpose**: Side-by-side provider comparison

**Key Features**:
- Simultaneous display of two providers
- Internal + provider-specific market names
- Clean comparison view (compare mode OFF)

---

### Screen 2: Event Detail View (Compare Mode)
![Compare Mode Active](04-event-detail-compare-mode.png)

**Purpose**: Highlighted difference detection

**Key Features**:
- Orange highlighting on all differences
- Name variation warnings
- Odds discrepancy indicators
- Explanatory notice

---

### Screen 3: Market Detail & Message Inspection
![Side Panel](05-market-detail-side-panel.png)

**Purpose**: Technical message inspection

**Key Features**:
- 800px side panel overlay
- Raw & transformed JSON display
- Mapping visualization
- Copy-to-clipboard functionality

---

## Design System

### Colors
- Blue: `#0d6efd` (Primary)
- Green: `#198754` (Success/Active)
- Orange: `#fd7e14` (Warning/Difference)
- Purple: `#6f42c1` (Mapping)
- Yellow: `#ffc107` (Highlight)

### Typography
- UI Text: Manrope
- Code/Data: JetBrains Mono

### Status Badges
- Active: Green
- Suspended: Yellow
- Closed: Gray
- Resulted: Gray

See complete design system in mockup README.
```

---

## 🎫 JIRA Ticket Template

```markdown
**Summary**: Implement Feed Testing Tool UI - Events List View

**Description**:
Build the Events List View (Screen 1) for the Feed Integration Testing Tool.

**Visual Design**:
Mockup: `/docs/mockups/feed-testing-tool/01-events-list.png`
Interactive: `/docs/mockups/feed-testing-tool/feed-testing-tool-wireframes.html`

**Requirements**:
- Implement filterable events table
- Add provider badge display
- Create dual navigation icons (info ⓘ, arrow →)
- Real-time event count updates
- Responsive layout matching mockup design

**Acceptance Criteria**:
- [ ] Table displays all columns from mockup
- [ ] Filters work in real-time
- [ ] Provider badges show all offering providers
- [ ] Info icon opens side panel
- [ ] Arrow icon navigates to event detail
- [ ] Event count updates with filters
- [ ] Visual design matches mockup

**Attachments**:
- 01-events-list.png
- feed-testing-tool-wireframes.html

**Story Points**: 5
**Sprint**: [Your Sprint]
```

---

## 💬 Slack/Teams Message Templates

### To Stakeholders:
```
Hi team! 👋

The Feed Testing Tool mockups are now ready for review:

📁 Location: /docs/mockups/feed-testing-tool/
🎨 Interactive: feed-testing-tool-wireframes.html
📖 Docs: README.md

Key features:
✅ Events list with real-time filtering
✅ Single/Multi-provider comparison
✅ Compare mode with difference highlighting
✅ Side panel for message inspection

Please review and share feedback by [DATE]. You can open the HTML file locally or view screenshots in the folder.
```

### To Development Team:
```
Dev team! 🚀

Feed Testing Tool mockups are ready:

Location: /docs/mockups/feed-testing-tool/
- Interactive mockup (HTML) - shows all interactions
- Complete README - technical specs & design decisions
- Screenshots - visual reference

Features to implement:
1. Events list (Screen 1)
2. Event detail with provider toggle (Screen 2)
3. Compare mode with highlighting (Screen 2)
4. Side panel for messages (Screen 3)

The HTML mockup has working filters, toggles, and buttons to demonstrate expected behavior. Check it out before sprint planning!
```

### To QA Team:
```
QA Team! 🧪

New testing tool mockups available:

📂 /docs/mockups/feed-testing-tool/
📱 Interactive prototype: feed-testing-tool-wireframes.html

This tool will help you:
✓ Test feed integrations from all providers
✓ Compare provider data side-by-side
✓ Validate mappings and transformations
✓ Inspect raw/transformed messages

Review the mockups and let me know if any test scenarios are missing!
```

---

## ✅ Quick Copy-Paste Snippets

### For PRD Table of Contents:
```markdown
- [Visual Design & Mockups](#visual-design--mockups)
  - [Screen 1: Events List](#screen-1-events-list)
  - [Screen 2: Event Detail](#screen-2-event-detail)
  - [Screen 3: Market Detail](#screen-3-market-detail)
  - [Interactive Mockup](#interactive-mockup)
```

### For User Story Link:
```markdown
**Mockup Reference**: [View Mockup](/docs/mockups/feed-testing-tool/)
```

### For Pull Request Description:
```markdown
## Visual Reference
Mockups: `/docs/mockups/feed-testing-tool/`

This PR implements the UI shown in:
- `02-event-detail-single-provider.png` (Single provider view)
- `03-event-detail-multi-provider.png` (Multi-provider comparison)

Interactive behavior matches: `feed-testing-tool-wireframes.html` → Event Detail View tab
```

### For Code Comment:
```javascript
// UI Layout Reference: /docs/mockups/feed-testing-tool/03-event-detail-multi-provider.png
// Interactive behavior: feed-testing-tool-wireframes.html (Multi-Provider mode)
```

---

**Last Updated**: December 2025
