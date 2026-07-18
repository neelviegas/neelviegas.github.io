# neelviegas.github.io — Portfolio

Static portfolio site (plain HTML/CSS, no build step) for GitHub Pages.

## Repo layout

```
neelviegas.github.io/
├── index.html
├── projects.html
├── cv.html
├── style.css
├── README.md
├── .nojekyll
└── media/            ← your Media folder, renamed to lowercase "media"
    ├── Chair Project/
    ├── Curtain Project/
    ├── Injector Redesign/
    ├── Other/
    └── Thrust Analysis/
```

The site reads all images, videos, and the CV straight out of `media/`.
Nothing is duplicated or renamed — the HTML points at your real filenames.

## Deploy

1. Rename your `Media` folder to **`media`** (lowercase — GitHub Pages URLs are
   case-sensitive, so this avoids broken images on the live site).
2. Put `media/` and all the site files at the **root** of your
   `neelviegas.github.io` repo (so `index.html` is at the top level).
3. Commit and push to `main`.
4. GitHub Pages serves it at `https://neelviegas.github.io`.
   (Settings → Pages → Deploy from branch → `main` / root, if not already set.)

The `.nojekyll` file is included so GitHub serves the `media/` folder as-is
(folders with spaces work fine; Jekyll would otherwise interfere).

## What's wired to what

| Page / slot | File used |
|---|---|
| Home — Thrust card | `media/Thrust Analysis/massflowrate data.png` |
| Home — Curtains card | `media/Curtain Project/fully assembled.jpg` |
| Home — Injector card | `media/Injector Redesign/benchscale.png` |
| Home — Chair card | `media/Chair Project/chair_assembly.jpeg` |
| Home — P&W card | `media/Other/Catia_injector_FEA_topface.png` |
| Projects — Thrust | massflowrate data · upright graphs · Test Stand Hotfire pic |
| Projects — Injector | benchscale · fullscale |
| Projects — Curtains | curcuit · prototypes · fully assembled · fully assembled (from top) · working vid.mp4 |
| Projects — Chair | chair_assembly · Final_seat_piston_vid.mp4 · Final_armrests_video.mp4 |
| CV — Download button | `media/Other/CV_Neel_Viegas.pdf` |

## Spare files (in your folder, not yet shown)

These are available if you want to add them later:
`Final Assembly Curtains.mp4`, `Catia_injector_FEA_bottomface.png`,
`MRT_Logo_RG.png`, `McGill-Rocket-3.jpg`,
`ScreenRecording_04-26-2026 08-56-20_1.mov`.

## The one placeholder left

The **Local AI Model** project has no image in your folder yet. It shows a hatched
placeholder pointing at `media/Other/ai_cover.png` (home) and
`media/Other/ai_pipeline.png` (projects). Drop files with those names into
`media/Other/`, then in the HTML replace the `<div class="ph">…</div>` block with:

```html
<img src="media/Other/ai_cover.png" alt="Local AI model">
```

## Notes on video

Videos use `preload="none"` (click-to-play) so pages stay fast. `working vid.mp4`
is ~37 MB — within GitHub's 100 MB limit, but the single biggest file. If load
time ever bothers you, compress it or host on YouTube and embed instead.
