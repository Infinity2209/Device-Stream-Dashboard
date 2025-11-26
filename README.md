# Device Stream Dashboard Project

## Overview
This project is a live-ish dashboard for visualizing and analyzing device data streams. It supports real-time Server-Sent Events (SSE) streaming and JSONL data replay to present key performance indicators (KPIs) and insights.

## Features
- Live SSE data streaming from `http://localhost:8080/stream`
- Replay mode for JSONL files with playback controls (play, pause, speed)
- Interactive kW trend chart using Chart.js
- Dynamic KPI calculations: uptime, average power, energy, power factor, throughput, phase imbalance
- Auto-insights (conceptual placeholders)
- Visual gap detection (data gap > 10 seconds) indicator
- Export visible data window to CSV
- Responsive and accessible user interface with ARIA and semantic landmarks

## Tech Stack
- Node.js for SSE streaming server (live_sse_server.js)
- HTML, CSS, JavaScript for frontend
- Chart.js for chart visualizations
- Luxon for date/time handling
- Server-Sent Events (EventSource API) for live data consumption

## Setup & Running Locally

1. Clone the repository or copy project files.

2. Ensure you have Node.js installed.

3. Start the live SSE data server:
   ```
   node "live_sse_server (1).js"
   ```
   This starts a local SSE server at: `http://localhost:8080/stream`

4. Open `dashboard.html` in a modern browser.

5. Use the "Live Stream" button to connect to the live SSE data feed.

6. Alternatively, use "Replay" mode by uploading a JSONL file and employing play/pause controls.

## KPI Definitions

KPIs are computed over a sliding visible data window (e.g. last 5/15/30 minutes):

- Uptime %, Idle %, Off %: Percentage of time in each state (RUN, IDLE, OFF)
- Average kW power
- Energy (kWh): Difference of max and min kwh_total in window
- Power Factor average over RUN + IDLE states
- Production throughput (units per minute)
- Phase Imbalance % of currents

## Testing & Validation

- Fully tested live streaming and replay functionalities.
- Validated KPI calculations and chart updates.
- Checked gap detection visual alert.
- Verified CSV export of visible data.
- Confirmed responsiveness and accessibility features.

## Deliverables

- Fully functional dashboard on `dashboard.html`.
- Live SSE simulator in `live_sse_server (1).js`.
- Replay capabilities with JSONL files.
- Detailed README with usage instructions and technical overview.

## Notes

- Adapt speed controls and replay options as needed.
- Future enhancements may include additional charts and improved auto-insights.

---

Feel free to reach out for issues or feedback.
