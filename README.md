# McAllister Journal (1831–1833)

An interactive single-page historical web application, nautical chart, and sequential journal reader chronicling the Atlantic and Caribbean trading voyages of **Captain George C. McAllister** (St. Andrews, New Brunswick) aboard the *Brig Keziah*, *Brig Emerald*, and *Brig Woodbine*.

---

## Features

### 1. Interactive Nautical Map & Voyage Tracks
- **82 Daily Log Coordinate Observations**: Plotted along historical routes with custom parchment-styled nautical cartography powered by Leaflet.js.
- **True Nautical Coordinates**: Coordinates are parsed directly from historical log entries into accurate degrees and minutes (`DD° MM' N/S, DD° MM' E/W`) for drawer displays and map tooltips.
- **Vessel Route Filtering**: Filter map tracks and milestones by vessel:
  - **Brig Keziah (1831)**: St. Andrews $\rightarrow$ Caribbean run & May 1831 return via Halifax.
  - **Brig Keziah (August 1831)**: Second Barbados voyage ending in the Great Barbados Hurricane.
  - **Brig Emerald (September 1831)**: Rescue passage bringing McAllister and salvaged cargo back to New Brunswick.
  - **Brig Woodbine (1832–1833)**: Subsequent trading voyages between St. Andrews and Barbados.

### 2. Guided Tour & Text-to-Speech Engine
- **Seamless Tour Resumption**: Starting the tour or pressing play at the bottom continues directly from the most recently selected coordinate or notable milestone.
- **Immediate Speech Switching**: Clicking any map coordinate, milestone badge, reader link, or navigation button immediately halts ongoing speech and begins narrating the new selection.
- **3-Second Comprehension Pause**: During automated tour playback, pauses for 3 seconds after speech completion before auto-advancing to the next stop.
- **Phonetic Normalization (`NAV_SPEECH_REPLACEMENTS`)**: Automatic expansion of maritime abbreviations for clear browser Text-to-Speech pronunciation:
  - **Navigational Coordinates**: Expands patterns like `L.a.t. 27 58N. Long 55'50W` into *"Latitude 27 degrees 58 North, Longitude 55 degrees 50 West"*.
  - **Observation Prefixes**: Formats `Lat. by Obs`, `Obs. Lat.`, and `Lat. obsd.` into natural spoken words (*"Latitude by Observation"*, *"Observed Latitude"*).
  - **Wind & Compass Points**: Converts 32-point compass abbreviations (e.g. `Wind W.S.W.` $\rightarrow$ *"Wind West South West"*, `Wind E. N.E.` $\rightarrow$ *"Wind East North East"*, `steering N by E` $\rightarrow$ *"steering North by East"*).
  - **Direct Narration**: Reads Captain McAllister's journal entry directly without redundant position preambles.

### 3. Integrated Notable Points of Interest
- **16 Major Historical Milestones**: Key voyage events (such as the *70-Hour Atlantic Gale*, *Crossing the Tropic of Cancer*, *Dragon's Mouth Night Transit*, and *The Great Barbados Hurricane*) are linked into the daily timeline.
- **Dual Map Highlighting & Rich Summaries**: Coordinates corresponding to notable milestones display contextual event summaries and pulse both the coordinate dot and milestone badge on the map.

### 4. Sequential Journal Reader
- Searchable full-text OCR transcriptions of historical documents (Documents 001–060).
- Clickable coordinate badges that immediately fly the map to the location, open the observation drawer, and narrate the log excerpt.

---

## Local Development & Usage

Open `index.html` directly in any modern web browser, or serve it locally:

```bash
# Start a local static HTTP server
python3 -m http.server 8000
```

Navigate to `http://localhost:8000` in your web browser.

---

## Project Structure

- `index.html` — Standalone single-page application containing markup, Tailwind CSS styling, Leaflet map logic, TTS processing engine, and full dataset (`APP_DATA`).
- `README.md` — Project documentation and feature reference.
