# Emberwake — full-game zip assembly (v2.29 snapshot)

Everything Ryan needs to play the COMPLETE game locally, with all art and
audio. The GitHub Pages version was dropping image assets (black arenas,
blank Luna portrait) — these zips contain every file, verified present.

## The five pieces

| Zip | Contents |
|-----|----------|
| `emberwake-full-1of5-index.zip` | `index.html` + this file (both at the top level of the zip) |
| `emberwake-full-2of5-frames-a.zip` | 152 character-frame PNGs, stored under `assets/` |
| `emberwake-full-3of5-frames-b.zip` | 159 character-frame PNGs, stored under `assets/` |
| `emberwake-full-4of5-art.zip` | 57 JPGs — arena backgrounds, banners, portraits — stored under `assets/` |
| `emberwake-full-5of5-audio.zip` | 50 MP3s — music, ambience, narration, SFX — stored under `assets/` |

## Assembly

1. Create one empty folder, e.g. `emberwake-full/`.
2. Unzip **all five** zips into that folder. Every zip stores relative paths,
   so extraction recreates the layout automatically — no manual folder
   creation needed:
   - `emberwake-full/index.html`
   - `emberwake-full/assets/` holding all 418 game assets
   - `emberwake-full/ASSEMBLY.md` (this file — documentation only)
3. **Verify** before playing. The game itself is exactly **419 files**:
   1 × `index.html` + 418 files inside `assets/`. This ASSEMBLY.md is
   documentation and is NOT part of that count, so leave it out of the game
   folder (or just ignore it when counting). Quick spot-checks that the
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
