# Event Management Guide

The events page now dynamically loads events from `events.csv`. Whenever you update the CSV file, the changes automatically reflect on the website.

## Adding/Editing Events

Edit `events.csv` with the following columns:

| Column | Description | Example |
|--------|-------------|---------|
| `date` | Event date | `Dec 15 2025` |
| `title` | Event title | `JOSAA Seat Allotment Decoded` |
| `time` | Event time (IST) | `2:00 PM - 3:30 PM IST` |
| `description` | Event description | `Understand the complete JOSAA seat allotment process...` |
| `speakers` | Speaker names | `IIT Counselors` |
| `mode` | Event mode | `Online (Zoom)` or `Online + In-Person` |
| `duration` | Event duration | `90 minutes` |
| `type` | Event type badge | `Webinar`, `Seminar`, `Workshop`, `Panel Discussion` |
| `category` | Event category | `JOSAA`, `NRI`, `Trends`, `Career` |

## Example CSV Entry

```
date,title,time,description,speakers,mode,duration,type,category
Dec 15 2025,JOSAA Seat Allotment Decoded,2:00 PM - 3:30 PM IST,Understand the complete JOSAA seat allotment process...,IIT Counselors,Online (Zoom),90 minutes,Webinar,JOSAA
```

## How It Works

1. **Page Load**: When `events.html` loads, it fetches `events.csv`
2. **CSV Parsing**: JavaScript parses the CSV into event objects
3. **Rendering**: Events are dynamically rendered as cards with icons
4. **Form Dropdown**: The registration form dropdown auto-populates with all events

## Deployment

After editing `events.csv`:
1. Save the file locally
2. Commit: `git add events.csv && git commit -m "Update events"`
3. Push: `git push origin main`
4. Render automatically deploys within 1-2 minutes
5. Visit `https://rkrrahman-786.github.io/events.html` to see changes

## Tips

- Keep descriptions concise and on one line (no line breaks in CSV)
- Use consistent date format: `Mon DD YYYY` (e.g., `Dec 15 2025`)
- Type values: `Webinar`, `Seminar`, `Workshop`, `Panel Discussion`
- Icons are auto-generated - no need to add them manually
