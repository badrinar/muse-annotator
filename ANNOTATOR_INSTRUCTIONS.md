# Muse Heart Sound Annotation — Annotator Guide

Thanks for helping us build the Muse heart sound dataset. This page is everything you need to get started. It should take about 5 minutes to read.

---

## What you're doing

You'll listen to short recordings of heartbeats and mark specific sounds in each one:

- **S1** — the "lub" at the start of each beat
- **S2** — the "dub" at the end of each beat
- **S3** — a soft extra beat that sometimes follows S2 ("lub-dub-dup")
- **S4** — a soft extra beat that sometimes precedes S1 ("dup-lub-dub")
- **Noise / artifact** — any portion that's unusable (handling, rustling, dropouts)

You don't need to diagnose anything. Just mark what you hear. If you're unsure, set confidence to Low and move on — that signal is useful to us.

---

## Getting started

1. **Open the tool**: `<TOOL_URL>`
2. **Sign in with Google** using the account we added to the test-user list. If you get a "this app isn't verified" screen, click *Advanced → Continue* — this is expected for internal tools.
3. When asked, grant the app permission to read and write files in your Drive.
4. **Paste your folder ID** into the "Assigned Drive folder ID" field:
   ```
   <FOLDER_ID>
   ```
5. **Enter your name** (pre-filled from Google — edit if you want).
6. Click **Load files & start**. You'll see a list of files on the left.

---

## The interface

### Left sidebar — file queue

Every file in your assigned folder. Each row shows the filename, a dataset tag, and a status chip (Pending, In Progress, Done, Skipped). Click a row to load that file.

Progress bar at the top: how many you've finished.

### Center — waveform and controls

- **Waveform** (the gold line): click anywhere on it to place a marker of the currently selected label type. Drag markers to adjust, right-click to delete.
- **Zoom**: scroll the mouse wheel over the waveform, or use the `−` / `+` buttons.
- **Transport** (below waveform):
  - Play / Pause (or press **Space**)
  - Loop: when on, plays the currently visible window over and over
  - Speed: 0.5× / 0.75× / 1×
  - Volume slider
  - Time display: current position / total length

### Label mode

The five colored buttons. Click one (or press a number key) to choose what kind of marker your next click places.

| Key | Label | Color |
|---|---|---|
| 1 | S1 | Blue |
| 2 | S2 | Green |
| 3 | S3 | Orange |
| 4 | S4 | Pink |
| N | Noise | Grey |

- **S1 and S2** are *point markers* — a single moment in time (the onset of the sound). Just click where you hear it.
- **S3 and S4** are *short regions* (~80 ms) — click to place, then drag the edges to fine-tune.
- **Noise** is a *free-length region* — click and drag on the waveform to select the duration.

### Annotation timeline

The dark strip below the waveform. Shows all your markers laid out on five tracks (S1, S2, S3, S4, Noise) so you can see the rhythm at a glance. Click anywhere on it to seek.

### Marker list

Table of every marker in the current file, sorted by time. Click a row to seek to it. Click the × to delete.

### Confidence and notes

- **Confidence**: Low / Medium / High (default Medium) — your overall confidence in this file's annotations.
- **Notes**: optional free text. Anything you'd want the Muse team to know about this recording ("heart rate feels fast", "stethoscope slipped at 5s", etc.).

### Reference panel

Click the **?** button (top right of the right edge) to open a panel with short definitions of S1 / S2 / S3 / S4 and a "Play reference clip" button for each. Use this any time you want to check what the sound is supposed to resemble. These clips are real recordings from the University of Michigan Heart Sound Library.

---

## How to annotate (typical flow)

1. Click a file in the queue → wait a second for the waveform to load.
2. **Listen through once at normal speed** without marking anything. Let your ear settle on the rhythm.
3. Switch to S1 mode (press `1`), play, and drop S1 markers on each "lub". Zoom in if onsets are hard to pick.
4. Switch to S2 mode (`2`) and drop S2 markers on each "dub".
5. Listen again — is there a soft third or fourth beat in between? Switch to S3 (`3`) or S4 (`4`) and drop regions. Pause the reference clip against the recording if you're unsure.
6. If any part is unusable (clipping, rustling, dropout), switch to Noise (`N`) and click-drag to cover it.
7. Set confidence. Add a note if anything's worth flagging.
8. Press **Enter** (or click **Save & Next**) to mark this file Done and move to the next Pending file.

**Skip files you genuinely can't annotate.** The Skip button marks the file Skipped and moves on. Don't force a bad annotation — skipping is useful data.

---

## Keyboard shortcuts

| Key | Action |
|---|---|
| Space | Play / Pause |
| 1 / 2 / 3 / 4 / N | Switch label mode (S1 / S2 / S3 / S4 / Noise) |
| Enter | Save & Next |
| Ctrl+Z (or Cmd+Z on Mac) | Undo last marker change |
| ← / → | Seek ±1 second |
| [ / ] | Jump to previous / next marker |
| ? | Toggle reference panel |

---

## Saving and exporting

**Your work is auto-saved** to your browser every time you add or move a marker. If you close the tab and come back later, you'll see a "Restore" banner — click it to pick up where you left off.

**When you're ready to submit**, click the **Export** button in the top-right of the header. This does two things at once:

1. Saves a JSON file to an `annotations/` subfolder inside your assigned Drive folder (automatic).
2. Downloads the same JSON to your computer as a backup.

You can Export any time — partway through is fine. Each Export overwrites the previous one for that day.

If the "Saved to Drive" message comes up red, the Drive upload failed (network hiccup or permission issue). The local download still works — email it to `<YOUR_EMAIL>` as a fallback.

---

## Troubleshooting

**"GOOGLE_CLIENT_ID is not configured"** — the URL you were given is wrong. Ask the team for the correct link.

**"Folder not accessible"** — your Google account hasn't been added to the Drive folder. Ask the team to share it with you.

**"This app isn't verified"** at sign-in — expected. Click *Advanced → Continue*. The tool is internal and only your team has access.

**Waveform doesn't load / audio won't play** — reload the page. If it persists, try a different browser (Chrome and Firefox are best-tested; Safari works but is fussier).

**I placed a marker in the wrong spot** — drag it, or right-click to delete. Undo with Ctrl/Cmd+Z — the undo history is unlimited within a file session.

**I accidentally marked a file Done** — no problem, click it in the queue again, fix it, Save & Next will re-save.

**My whole session vanished** — check the Restore banner on the next load. If the banner doesn't appear, your browser probably cleared localStorage (private-window mode does this). Contact the team.

---

## Questions

Anything confusing, broken, or worth flagging → email `<YOUR_EMAIL>`.

Thanks again for helping build this dataset.
