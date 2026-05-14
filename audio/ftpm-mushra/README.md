# FTPM MUSHRA audio

This folder holds the audio stimuli used by the MUSHRA listening test on
**`/articles/ftpm-sound-quality/`**.

## Required structure

```
audio/ftpm-mushra/
├── music/
│   ├── reference.mp3   # unprocessed reference (Let It Be excerpt)
│   ├── A.mp3           # hidden reference (= reference.mp3, FTPM   0.00 oct)
│   ├── B.mp3           # test stimulus, FTPM −0.26 oct
│   ├── C.mp3           # test stimulus, FTPM −0.43 oct
│   ├── D.mp3           # test stimulus, FTPM −0.63 oct
│   ├── E.mp3           # test stimulus, FTPM −0.81 oct
│   ├── F.mp3           # test stimulus, FTPM −0.98 oct
│   └── G.mp3           # anchor — linear FTPM −1.50 oct
└── speech/
    ├── reference.mp3   # unprocessed reference (Dickens excerpt)
    └── A.mp3 .. G.mp3  # same shifts as the music trial
```

These shifts match Condition 1 of Villejoubert et al. (JASA 159(4),
3358–3371, 2026) — see Sec. II.E and Fig. 4(A).

Filenames must match the `file:` paths in
[`_data/mushra_ftpm.yml`](../../_data/mushra_ftpm.yml).

## Uploading from the GitHub web UI

1. Navigate to `audio/ftpm-mushra/music/` in github.com
2. Click **Add file → Upload files**
3. Drag your `.mp3` / `.wav` / `.ogg` files in (filenames matter — see above)
4. Commit. The MUSHRA player at `/articles/ftpm-sound-quality/` picks them up
   on the next deploy (~60 s).

## Adding a new trial

1. Pick a folder name (e.g. `cello/`) and upload `reference.mp3`, `A.mp3`,
   `B.mp3`, …
2. Edit [`_data/mushra_ftpm.yml`](../../_data/mushra_ftpm.yml) — copy one of
   the existing `trials:` blocks, change `id`, `label`, `description`, and the
   file paths to your new folder. Commit. Done.

## Formats

- MP3, WAV, OGG, M4A — all work (HTML5 audio).
- Keep individual files under ~2 MB so the page loads quickly. ~10 s mono
  WAV at 44.1 kHz is ~880 KB; convert to 192 kbps MP3 to halve that.
- All stimuli within a trial **must be the same length** so the slider stays
  meaningful.
