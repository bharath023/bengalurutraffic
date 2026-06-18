# Bengaluru Traffic Analysis
### Data-driven analysis of Bengaluru's urban mobility crisis

**Dr. Bharath A.L.** · Senior Hydrologist · Canarys Automations Limited · Bengaluru

🔗 **Live site:** `https://bharathal.github.io/bengaluru-traffic-analysis`

---

## What this is

Three official datasets. Five interactive charts. One signal delay compounding table that hasn't been published anywhere before.

This repo contains all the analysis, visualisations, and interactive tools built for a LinkedIn article on Bengaluru's traffic crisis — and why ₹13,262 crore in flyovers won't fix it.

---

## Tools

| File | Description |
|---|---|
| [`index.html`](index.html) | Landing page — links all three tools |
| [`linkedin_carousel.html`](linkedin_carousel.html) | 9-slide carousel infographic for LinkedIn PDF post |
| [`signal_delay_calculator.html`](signal_delay_calculator.html) | Interactive signal delay cost calculator |
| [`bengaluru_metro_vs_vehicles.html`](bengaluru_metro_vs_vehicles.html) | Metro vs vehicle growth dashboard |

---

## Data sources

| # | Dataset | Source | Period |
|---|---|---|---|
| 1 | Karnataka Vehicle Registrations | Karnataka Transport Dept / [OpenCity](https://data.opencity.in) | 2017–2026 |
| 2 | Namma Metro OD Matrix | BMRCL (83 stations × 83 stations, hourly) | Aug 1–18, 2025 |
| 3 | BTP Signal Timing PDFs | Bengaluru City Traffic Police / [OpenCity](https://data.opencity.in/dataset/bengaluru-city-traffic-signal-data) | Nov 2025 |

---

## Key findings

```
Karnataka vehicle fleet (2026)   :  3,49,18,689  (+64.2% since 2017)
New vehicles added per day       :  3,965         (1 every 4.4 minutes)
Buses as % of fleet              :  0.7%          (101× fewer than 2-wheelers)

Namma Metro peak day (Aug 14)    :  8,40,311 journeys
Average weekday ridership        :  7,25,000
Weekday–weekend gap              :  −29.5%

Silk Board signal cycle (peak)   :  250s          (IRC:93 max = 180s, +70s violation)
Devagowda Petrol Bunk (peak)     :  285s          (+105s violation)
Silk Board on Sundays            :  173s          (−31%, same road, same geometry)

Signal delay · 10s · 3 sig/km · 10km commute:
  Annual hours lost per commuter  :  41.7 hr/yr
  Annual cost (₹12L IT salary)    :  ₹27,596/yr

City-wide aggregate (60L commuters, 10s delay):
  Annual person-hours destroyed   :  25 crore
  Economic cost (₹7L median)      :  ₹10,308 Cr/year
  B-SMILE flyover budget          :  ₹13,262 Cr (one-time)
```

---

## Signal delay compounding formula

Based on HCM 6th Edition (Transportation Research Board) and IRC:SP:41:

```
annual_hours_lost = delay_per_signal × signals_per_km × commute_km × 2 × 250 ÷ 3600
annual_cost       = annual_hours_lost × (salary ÷ 2000) + idle_fuel_cost
```

Where:
- `delay_per_signal` = extra seconds lost vs ideal free-flow passage (s)
- `signals_per_km` = 2–6 depending on Bengaluru zone
- `commute_km` = one-way distance
- `250` = working days per year
- `idle_fuel_cost` = annual_hours × 0.605 L/hr (fleet avg) × ₹103/L

---

## References

1. Karnataka Transport Dept — Vehicle Registration Data 2017–2026
2. BMRCL OD Matrix — Namma Metro Passenger Flow, Aug 2025
3. BTP Signal Timing PDFs — 100+ junctions (OpenCity, Nov 2025)
4. **IRC:93** — Peak signal cycle maximum: 180 seconds
5. **HCM 6th Edition** (TRB) — Saturation headway 2.2s
6. **IRC:SP:41** — Signal design guidelines
7. B-SMILE — ₹13,262 Cr, 75.6 km, 9 EPC tenders (May 2026)
8. TomTom Traffic Index 2024 — Bengaluru 3rd slowest, 18 km/hr
9. Singapore LTA — ERP 1998–2005: −44% CBD vehicles, −33% delay
10. BATCS / C-DAC — 165 AI junctions, 33% delay reduction (BTP, 2024)

---

## How to deploy on GitHub Pages

```bash
git init
git add .
git commit -m "Initial commit: Bengaluru traffic analysis"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/bengaluru-traffic-analysis.git
git push -u origin main
```

Then go to **Settings → Pages → Branch: main → / (root) → Save**

Your live URL: `https://YOUR_USERNAME.github.io/bengaluru-traffic-analysis`

---

## License

Data is from public government sources (Karnataka Transport Dept, BMRCL, BTP).
Analysis, code, and visualisations © Dr. Bharath A.L. 2026.
