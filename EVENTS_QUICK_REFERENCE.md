# Events System - Quick Reference

## Current Status ✅

**11 Sample Events Added and Verified**

The dynamic event system is fully functional and deployed.

---

## What Was Changed

### 1. `events.csv` - Event Data Source
**Location**: `/events.csv`

Contains 11 events with the following columns:
- `date` - Event date
- `title` - Event name
- `time` - IST time slot
- `description` - Event details
- `speakers` - Who will speak
- `mode` - Online/In-Person
- `duration` - Event length (90 minutes)
- `type` - Badge type (Webinar/Seminar/Workshop/Panel)
- `category` - Event category

### 2. `events.html` - Dynamic Page
**Location**: `/events.html`

JavaScript functions that run when page loads:
1. `loadEvents()` - Fetches events.csv
2. `parseCSV()` - Converts CSV to JavaScript objects
3. `renderEvents()` - Creates HTML cards dynamically
4. `populateEventDropdown()` - Fills form dropdown

### 3. `.gitignore` - Version Control
**Updated to track**: `events.csv` (so changes auto-deploy)

---

## All 11 Events Loaded

```
✓ JOSAA Seat Allotment Decoded (Dec 15 2025) - Webinar
✓ NRI Quota: Myths vs Reality (Dec 22 2025) - Seminar
✓ Engineering Cutoff Trends Analysis (Dec 29 2025) - Workshop
✓ Career Pathways in Engineering (Jan 10 2026) - Panel Discussion
✓ JEE Advanced Preparation Strategy (Jan 18 2026) - Workshop
✓ International NRI Student Panel (Jan 25 2026) - Panel Discussion
✓ BITSAT and VITEEE Masterclass (Feb 1 2026) - Webinar
✓ Scholarship and Financial Aid Guide (Feb 8 2026) - Seminar
✓ Hostel Life and Campus Culture (Feb 15 2026) - Webinar
✓ Internship and Placement Opportunities (Feb 22 2026) - Workshop
✓ Research and Innovation at IITs (Mar 1 2026) - Webinar
```

---

## How Events Display

### On Page Load
1. Browser loads `events.html`
2. JavaScript fetches `events.csv`
3. CSV is parsed into event objects
4. For each event, an HTML card is created:

```html
<div class="event-card">
  <span class="event-badge">Webinar</span>
  <div class="event-date">Dec 15 2025</div>
  <div class="event-time">
    <svg>...clock icon...</svg>
    2:00 PM - 3:30 PM IST
  </div>
  <h3>JOSAA Seat Allotment Decoded</h3>
  <p>Description text...</p>
  <div class="event-meta">
    <div>Icon Speakers</div>
    <div>Icon Mode</div>
    <div>Icon Duration</div>
  </div>
  <button>Register Now</button>
</div>
```

### Visual Result
- Grid layout (3-4 cards per row on desktop)
- Professional SVG icons (not emojis)
- Golden gradient styling
- Hover animations
- Responsive on mobile

### Form Dropdown
Auto-populated with:
```
Choose an event
├─ JOSAA Seat Allotment Decoded (Dec 15 2025)
├─ NRI Quota: Myths vs Reality (Dec 22 2025)
├─ Engineering Cutoff Trends Analysis (Dec 29 2025)
├─ Career Pathways in Engineering (Jan 10 2026)
├─ JEE Advanced Preparation Strategy (Jan 18 2026)
├─ International NRI Student Panel (Jan 25 2026)
├─ BITSAT and VITEEE Masterclass (Feb 1 2026)
├─ Scholarship and Financial Aid Guide (Feb 8 2026)
├─ Hostel Life and Campus Culture (Feb 15 2026)
├─ Internship and Placement Opportunities (Feb 22 2026)
└─ Research and Innovation at IITs (Mar 1 2026)
```

---

## To Test Live

Visit: `https://rkrrahman-786.github.io/events.html`

Wait 1-2 minutes after git push for Render to deploy.

---

## To Add New Events

### Method: Edit CSV Directly

1. **Open**: `events.csv` in any text editor
2. **Add row**: 
   ```csv
   Jan 15 2026,New Event Title,1:00 PM - 2:30 PM IST,Event description here,Speakers Name,Online (Zoom),90 minutes,Webinar,Category
   ```
3. **Save** the file
4. **Commit**:
   ```bash
   git add events.csv
   git commit -m "Add new event"
   git push origin main
   ```
5. **Wait** 1-2 minutes
6. **Refresh** https://rkrrahman-786.github.io/events.html

The new event appears automatically! No HTML editing needed.

---

## Important Notes

⚠️ **CSV Format Rules**:
- Headers must be: `date,title,time,description,speakers,mode,duration,type,category`
- Each row = one event
- Descriptions should NOT contain commas (use semicolons instead)
- Descriptions should be on ONE line (no line breaks)
- All fields are required
- Date format: `Mon DD YYYY` (e.g., `Jan 15 2026`)

✅ **Type options**:
- `Webinar`
- `Seminar`
- `Workshop`
- `Panel Discussion`

✅ **Icons auto-generated** for:
- Time (clock)
- Speakers (people group)
- Mode (location pin)
- Duration (hourglass/clock)

---

## Files in System

```
/events.csv                 ← Event data (edit this to add events)
/events.html               ← Event display page (auto-loads CSV)
/EVENT_MANAGEMENT.md       ← Full management guide
/EVENTS_VERIFICATION.md    ← Detailed verification report
/test-events.html          ← Testing/debugging tool
```

---

## Deployment Status

✅ All 11 events committed and pushed
✅ events.csv tracked by git
✅ .gitignore updated
✅ Ready for live testing on Render

Next deployment: Automatic within 1-2 minutes of git push.
