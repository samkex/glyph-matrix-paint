# Glyph Matrix Paint

A browser tool for drawing LED patterns for the Glyph Matrix on Nothing Phone (3) and Phone (4a) Pro.

Start with a blank canvas or the Orbit Dial template. Export your drawing as SVG or PNG.

**[Open Glyph Matrix Paint](https://glyph-matrix-paint.vercel.app)**

![Glyph Matrix Paint showing the Orbit Dial template on Phone (3)](docs/hero.png)

## Draw

Choose a phone, then click or drag across the LEDs. On Blank canvas each phone keeps its own drawing and undo history.

| Phone | Grid | LEDs |
|---|---|---|
| Phone (3) | 25 × 25 | 489 |
| Phone (4a) Pro | 13 × 13 | 137 |

Click an LED to set it to the selected brush level. Click it again at the same level to clear it. A drag paints or clears according to the first position you touch.

| Control | Action |
|---|---|
| Clear | Turn all LEDs off |
| Invert | Turn lit LEDs off and dark LEDs on at the brush level |
| Undo | Go back through up to 64 edits for the selected phone |
| Grid | Show or hide the centre axes and diagonal guides |
| Mirror | Reflect strokes left to right, top to bottom, or both |
| Brush | Choose Full or Dim brightness |

Undo with ⌘+Z or Ctrl+Z. Redo with Shift+⌘+Z, Ctrl+Shift+Z or Ctrl+Y. A new edit clears the redo history.

## Start with a template

Template 01 is based on [Orbit Dial](https://github.com/samkex/orbit-dial): twelve hour marks and a minute mark inside them.

Selecting it switches to Phone (3) and starts at 10:08. Switching phones loads that phone's defaults and replaces its drawing with the dial.

| Setting | Phone (3) | Phone (4a) Pro |
|---|---|---|
| Scale length | 3 | 2 |
| Minute orbit | 6 | 1.5 |
| Scale dim | 575 | 575 |
| Minute size | 2 | 2 |

Adjust the sliders to change the dial. Solid draws the minute mark as a block of LEDs. Smoothed distributes it across neighbouring LEDs; Minute size does not apply in this mode. Marks outside the panel are clipped, so a large Minute orbit can hide the minute mark.

To edit the dial by hand, choose Blank canvas or start drawing. Clear and Invert also leave template mode and act on the current dial.

Undo while the template is active restores the drawing it replaced. After painting, Clear or Invert, Undo reverses that edit first.

## Export

- **Download SVG:** 520 × 520, with a black disc and one square per LED.
- **Copy PNG:** 1040 × 1040, ready to paste into a document.

Both use the current drawing. Grid guides are excluded.

## Display

The controls sit beside the canvas in a wide window and below it in a narrow one.

Choose English, Japanese or Traditional Chinese (Hong Kong) in the panel. The page starts in light mode; use the theme button to switch to dark.

## About the preview

The preview follows each phone's LED layout. Screen brightness does not reproduce the physical LEDs, so use it to compose a pattern rather than judge its final brightness.

Scale dim uses a range of 0 to 2047, based on the frame values reported in Orbit Dial's documentation. The browser renders these as 0 to 255. The default of 575 was chosen by observing the physical LEDs.

Orbit Dial measured the 0 to 2047 range on Phone (4a) Pro with Nothing OS C5.0-260902-1559 and Glyph service 3.6.0. On Phone (3) with Nothing OS C5.0-260921-0124 and Glyph service 5.0.0, it reports that the panel takes the full range. Both cite the Glyph Matrix Developer Kit at commit `999b1143`.

Device specifications come from Nothing's [Glyph Matrix Developer Kit](https://github.com/Nothing-Developer-Programme/GlyphMatrix-Developer-Kit). The phone-specific defaults and brightness observations are documented in Orbit Dial's [Phone (3)](https://github.com/samkex/orbit-dial/blob/main/README-phone-3.md) and [Phone (4a) Pro](https://github.com/samkex/orbit-dial/blob/main/README.md) pages.

## Licence

Copyright © 2026 Keith Chan. All rights reserved. The page is free to use; its design, code, text and images are not licensed for reuse. A drawing you make with it and export is yours. A frame drawn by Template 01 is Orbit Dial's dial, under Orbit Dial's own licence and notice. See [LICENSE](LICENSE).

Nothing's icons are excluded from this notice. Geist and Geist Mono are licensed under the SIL Open Font License 1.1, reproduced inside the page.
