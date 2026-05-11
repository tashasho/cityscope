# ◈ CITYSCOPE

### _what if Google Maps had a baby with Stardew Valley... and that baby only cared about cool events?_

> Pixel art event maps for Indian cities. Zero dependencies. Zero build steps. 100% vibes.

**[🎮 Play the Demo →](https://cityscope-tau.vercel.app)**

---

## 🤔 wait, what is this?

CITYSCOPE renders **live events** happening across Indian cities as a fully interactive, retro pixel art game world — complete with auto-rickshaws, stray dogs, metro trains, monsoon rain, and fireflies at night.

Think: you open a map. It looks like a 90s RPG. You zoom into Koramangala and suddenly you're looking at a pixel-art street view of that AI meetup happening on Saturday. Click a venue diamond and boom — event details, attendee count, ticket status, the works.

**No React. No Tailwind. No npm install that takes 47 minutes.**
Just raw HTML5 Canvas and questionable amounts of JavaScript in a single file.

---

## 🏙️ Cities

| City | Status | Events | Venues | Sources | Vibe |
|------|--------|--------|--------|---------|------|
| **Bengaluru** | ✅ Live | 75+ | 30 | 5 | _"startup central meets garden city"_ |
| **Mumbai** | ✅ Live | 45+ | 24 | 7 | _"peninsula of chaos and concerts"_ |
| **Delhi NCR** | 🚧 WIP | — | — | — | _"mapping in progress... send chai"_ |

---

## ✨ Features (yes, all of these exist in a single HTML file)

🗺️ **Phase 1 — The World**
Neighborhood-colored buildings, 3 species of trees (banyan, gulmohar, palm), rooftop water tanks, flyovers, and zone-specific architecture. Koramangala looks different from Whitefield. As it should.

🏃 **Phase 2 — It's Alive**
Auto-rickshaws honking down roads, stray dogs chilling near buildings, bird flocks migrating across the sky, and a ☂️ monsoon rain toggle because... Bangalore.

🚇 **Phase 3 — Landmarks & Transit**
Namma Metro (purple + green lines!) with actual moving trains. Vidhana Soudha. Bangalore Palace. Traffic signals that cycle through red/yellow/green. The eternal red light at Silk Board is accurately represented.

🏘️ **Phase 4 — Street View**
Click any venue and get an auto-generated pixel art street scene — buildings, people, rickshaws, and category-specific details (♪ notes float near music venues, steam rises from food spots).

✨ **Phase 5 — The Polish**
Fireflies in parks at night. Musical notes drifting from concert venues. Steam from food stalls. Minimap. Zoom/pan. Day/night cycle with a real clock. This is where the ✨magic✨ happens.

---

## 🎮 Controls

| Do this | Get this |
|---------|---------|
| `Scroll wheel` | Zoom in/out (0.5× – 4×) |
| `Click + drag` | Pan around the map |
| `Click a venue ◇` | Auto-zoom + event panel + street view |
| `☀/☾` button | Toggle day/night (windows light up!) |
| `☂` button | Toggle monsoon rain |
| `⌂` button | Reset view |
| `📋` button | Grid overlay of ALL events |
| Filter bar | Filter by source or category |

---

## 🚀 Run It

```bash
git clone https://github.com/tashasho/cityscope.git
cd cityscope
npx serve public -l 3000
# Open http://localhost:3000 and lose 2 hours of your life
```

Or just open `public/index.html` in your browser. It's literally just HTML files. We don't gatekeep here.

### Deploy Anywhere

```bash
# Vercel (recommended, it's free)
npx vercel --prod

# GitHub Pages
# Settings → Pages → Source: main branch, /public folder
# Live at https://USERNAME.github.io/cityscope

# Netlify
# Drag /public folder to netlify.com/drop. Done. Go get coffee.
```

---

## 📁 Project Structure

```
cityscope/
├── public/
│   ├── index.html              # Landing page — animated city selector
│   ├── submit.html             # Submit your city form
│   ├── feedback.html           # Feedback form
│   └── cities/
│       ├── bangalore.html      # Bengaluru map (~700 lines of pure art)
│       ├── mumbai.html         # Mumbai map (peninsula rendering is *chef's kiss*)
│       └── delhi.html          # Delhi NCR (WIP — accepting PRs & prayers)
├── package.json                # npm scripts (just `serve`, nothing fancy)
├── vercel.json                 # Vercel config
└── README.md                   # You are here. Hi. 👋
```

**Each city = one self-contained HTML file.** No bundler. No transpiler. No existential crisis about which framework to use. Just `<canvas>` doing god's work at 60fps.

---

## 📡 Event Sources

We aggregate from **11+ platforms** so you don't have to check 11 tabs:

**Bengaluru**: [Luma](https://lu.ma) · [Putting Scene](https://puttingscene.com) · [Your Third Place](https://www.yourthirdplace.in/) · [AllEvents](https://allevents.in/bangalore) · [District](https://www.district.in/)

**Mumbai**: [BookMyShow](https://in.bookmyshow.com) · [Luma](https://lu.ma) · [District](https://www.district.in/) · [AllEvents](https://allevents.in/mumbai) · [eChai](https://echai.ventures) · [Meetup](https://www.meetup.com) · [Time Out](https://www.timeout.com/mumbai)

---

## 🔧 Adding Events

Each city has a venues array `V`. Here's the format:

```javascript
{
  id: 42,
  ...geo(12.976, 77.592),        // Real lat/lng → pixel coordinates
  nm: "Venue Name\nNeighborhood",
  cat: 'tech',                    // tech | food | comedy | music | art | social | wellness
  src: 'luma',                    // Source platform
  lat: 12.976, lng: 77.592,
  vibe: '"hipster cafes" — Hoodmaps',  // Optional sass
  ev: [{
    t: "Event Title",
    by: "Organizer",
    d: "Date · Time",
    p: "Free",                    // or "₹500" or "SOLD OUT"
    a: 42, c: 50,                 // Attendees / Capacity
    tg: ['AI', 'buildathon'],     // Tags
    s: 'o'                        // 'o' = open, 'x' = sold out, 'w' = waitlist
  }]
}
```

---

## 🤝 Want to Help?

We don't want PRs. We want **event sources**.

### 📝 Submit Your City

Know cool event platforms in your city? Drop them in our form — city name, event source URLs, neighborhoods worth mapping. Once we collect enough sources for a city, we'll build the pixel map and make it live.

**[▸ SUBMIT CITY SOURCES](https://cityscope.vercel.app/submit)**

Currently scouting: **Delhi NCR** · Hyderabad · Chennai · Pune · Kolkata · Jaipur · Ahmedabad · Kochi · Goa

### 💬 Drop Feedback

Found a bug? Have a feature idea? Just want to say nice things? We actually read every response.

**[▸ SEND FEEDBACK](https://cityscope.vercel.app/feedback)**

No GitHub account needed. Anonymous submissions welcome.

---

## 🧠 How It Works (for the nerds)

- **Deterministic hash function** generates consistent tile variations from row/column coordinates — same pixel art every frame, no stored sprites
- **Real GPS coordinates** mapped to tile grid via linear interpolation within a city bounding box
- **Single `requestAnimationFrame` loop** renders everything: tiles, buildings, roads, vehicles, weather, particles, markers, UI
- **Zero external assets** — all graphics are procedurally drawn with `fillRect` and basic shapes
- **Canvas transform** for zoom/pan — the map is drawn at native resolution, CSS transform handles the rest

---

## 📄 License

MIT — fork it, remix it, make one for your city, put it on your portfolio, impress your crush, whatever. Just have fun.

---

<p align="center">
  <i>Built with ♥, <code>fillRect()</code>, and an mass quantities of mass chai ☕</i>
  <br><br>
  <b>◈ CITYSCOPE v1.0</b>
  <br>
  <sub>zero dependencies · pure canvas · mass vibes</sub>
</p>
