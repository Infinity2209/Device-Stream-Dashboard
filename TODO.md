# TODO - Device Stream Challenge

## Goal
- Show a live-ish dashboard from device data stream (SSE live or Replay mode)
- Surface meaningful KPIs and 3 auto-insights

## KPIs (Calculated over currently visible window)
- Uptime %, Idle %, Off % based on state durations
- Average kW (power) over samples
- Energy (kWh) from kwh_total register difference
- PF average (ignoring OFF samples)
- Throughput (units/min) and rolling 60s rate
- Phase imbalance % based on current measures

## Auto-Insights (Pick any 3 and justify)
- Detect contiguous idle stretches ≥ 30 min (or shorter threshold for 20 min sample)
- Peak 15-min demand: rolling 15-min average of kW, report max & timestamp
- Low PF window: continuous span with pf < 0.8 for ≥ 5 min
- Phase imbalance: % imbalance > 15% for ≥ 2 min
- Base-load: median kW during OFF/IDLE with cost calculation

## Must-have visuals & behaviors
- Charts: kW trend + aligned state band (RUN/IDLE/OFF)
- Mini-charts for ir/iy/ib and vr/vy/vb
- Units/min bar or sparkline
- Gap detector: red badge if no data for > 10 seconds
- Export CSV for visible window with raw fields

## Performance & Accessibility (a11y)
- Lighthouse score (Desktop) ≥ 90
- Responsive design
- Semantic landmarks, alt text, adequate contrast (≥ 4.5:1)

## Deliverables
- Live URL
- GitHub repository
- README
- Lighthouse screenshot
- 2–3 minute demo video

## Notes
- Use either SSE live stream or replay mode from JSONL file
- Focus on grasping power, task decoding, smart scoping, creativity

Good luck!
