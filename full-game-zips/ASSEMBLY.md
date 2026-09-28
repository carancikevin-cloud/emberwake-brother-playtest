# Emberwake — full-game zip assembly (v2.29 snapshot)

Everything Ryan needs to play the COMPLETE game locally, with all art and
audio. The GitHub Pages version was dropping image assets (black arenas,
blank Luna portrait) — these zips contain every file, verified present.

## The five pieces

| Zip | Contents |
|-----|----------|
| `emberwake-full-1of5-index.zip` | `index.html` + this file |
| `emberwake-full-2of5-frames-a.zip` | 152 character-frame PNGs (half) |
| `emberwake-full-3of5-frames-b.zip` | 159 character-frame PNGs (half) |
| `emberwake-full-4of5-art.zip` | 57 JPGs — arena backgrounds, banners, portraits |
| `emberwake-full-5of5-audio.zip` | 50 MP3s — music, ambience, narration, SFX |

## Assembly

1. Create one empty folder, e.g. `emberwake-full/`.
2. Unzip **all five** zips into that folder. Every zip unpacks relative paths,
   so after all five: `emberwake-full/index.html` plus
   `emberwake-full/assets/` holding everything else.
3. **Verify** before playing: the folder must contain **419 files total**
   (1 `index.html` + 418 inside `assets/`). Quick spot-checks that the
   previously-dropped assets survived:
   - `assets/bg-gloamwood-*.jpg` exists (arena backgrounds)
   - `assets/luna-portrait-*.jpg` exists (Luna's portrait)

## Running it

A plain `file://` open may block asset loading — serve the folder over HTTP:

**On Ryan's PC** (pick one):
- `cd emberwake-full && python3 -m http.server 8000`, then open
  http://localhost:8000
- or `npx serve emberwake-full`

**On iPhone over the same Wi-Fi:**
1. Start the server on the PC as above.
2. Find the PC's LAN address (e.g. 192.168.1.42).
3. On the iPhone, open `http://192.168.1.42:8000` in Safari.
4. Share → Add to Home Screen for fullscreen play.

## Know before playing

- **v2.29 frozen snapshot.** The live build has moved on (route slice,
  Sanctuary contracts, sound fixes) — this is the complete *playable* game
  as it stood, not the latest.
- **Fresh state only.** No save transfers. The session is memory-only:
  export the save and any feedback notes **before** closing or refreshing.
- If anything breaks on reassembly or first boot, tell Mira exactly where —
  file count, which step, what the screen shows.
