# Pelé+Celeste Video Subtitles for DaVinci Resolve

## Files

| File | Cut | Language |
|---|---|---|
| `pele-celeste-15s-en.srt` | 15s | English |
| `pele-celeste-15s-es.srt` | 15s | Spanish |
| `pele-celeste-15s-pt.srt` | 15s | Portuguese |
| `pele-celeste-30s-en.srt` | 30s | English |
| `pele-celeste-30s-es.srt` | 30s | Spanish |
| `pele-celeste-30s-pt.srt` | 30s | Portuguese |

## DaVinci Resolve workflow

1. **Open project** in DaVinci Resolve (free Studio version is fine)
2. **Import the video** to Media Pool: drag `pele-celeste-15s-original.mp4` (or 30s version)
3. **Drop video to timeline** on Edit page
4. **Import subtitle file:** File → Import → Subtitle → select the matching `.srt`
5. **Subtitle track appears** as a new caption track on the timeline
6. **Style the subtitles** in Inspector:
   - Font: **Playfair Display Bold** (matches FC Mother brand)
   - Size: **48-56pt** for square (1080×1080), **40-48pt** for vertical (1080×1920)
   - Color: **#F7F2E6** (cream)
   - Background: black @ 60% opacity OR text shadow (3px navy `#25176F`, 0px offset, 6px blur)
   - Position: bottom-third, ~85% Y of canvas
   - Alignment: center
7. **Export multiple aspect ratios** via Deliver page:
   - **Square 1080×1080** (Meta Feed): preset "Custom" → 1080w × 1080h
   - **Vertical 1080×1920** (Reels/Stories): preset "Custom" → 1080w × 1920h
   - **Landscape 1920×1080** (YouTube/Twitter): preset "Custom" → 1920w × 1080h
8. **Export 3 languages × 3 aspect ratios = 9 files total**

## Naming convention for exports

`pele-celeste-[15s|30s]-[en|es|pt]-[square|vertical|landscape]-1080.mp4`

## Brand outro card (insert as last 2 seconds)

If you want a closing brand card on the videos:

1. Create a 2-second still image:
   - Navy `#25176F` background
   - FC Mother logo top-center
   - Gold serif "Be a Legend · Assist a Mother" centered
   - Cream "app.fcmother.com" caps below
2. Import to Media Pool, drop on timeline at end
3. Add fade-in 0.5s

(I can render the outro card PNGs directly if you want — say "render the outro cards" and I'll produce 3 versions × 3 aspect ratios.)

## Quick polish on the Color page (optional)

- Add subtle vignette: Power Window oval + lower exposure outside the window
- Lift navy in shadows by 5-8 (matches brand palette)
- Subtle grain in Resolve FX → "Texture/Film Grain" → 16mm preset for vintage feel

## Audio polish on Fairlight (optional)

- If source has noise: apply "Noise Reduction" preset
- Add brand audio bed if available — search "uplifting cinematic" stock music
- Duck audio to -3dB during subtitle reads

---

Total time in DaVinci: ~30-45 min for the full 9-file render pipeline (15s + 30s × 3 langs × 3 ratios). Without subtitle styling: ~15 min.
