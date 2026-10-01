# Auto B-roll for After Effects

**Script + voiceover in. A fully edited timeline out.**

An After Effects panel that reads a video script, listens to the voiceover, and automatically builds the
edit: B-roll clips, AI images and AI videos, subtitles, animated key phrases, and connecting-line
animations - every piece placed and trimmed exactly where the voice says it.

> Designed, directed and tested by **Bayzid Ahmad** (video editor & motion designer), built with AI coding assistance.
> The source code is private - this page shows what the tool does.

<p align="center">
  <img src="images/panel.png" alt="Auto B-roll panel" width="480">
</p>

---

## The problem

Faceless and explainer YouTube videos need a new visual every few seconds. For a 20-minute video that means
hundreds of clips and images to find, download, trim, place and time to the voice - hours of repetitive
work for every video.

## The solution

One panel inside After Effects that does the repetitive part, so the editor can focus on the creative part.

| Before | After |
|---|---|
| Search YouTube for every line | The AI plans every scene and finds matching clips |
| Download, trim and place by hand | Only the needed seconds are downloaded and placed on the timeline |
| Time every cut to the voice | Every scene starts exactly when its words are spoken |
| Make or buy images one by one | AI images in a consistent style, generated in parallel |
| Animate connecting lines by hand | Drag a rope between layers on a node board - done |

---

## Features

### Auto B-roll
- Reads `.txt` / `.docx` scripts; a new scene at every comma and full stop
- Listens to the voiceover (any audio format) and matches every line to the exact second
- Works on the whole script or only a chosen part
- For each scene the AI decides what explains it best: a **real video clip** or an **image**
- Image styles: Realistic, Stick figure, Illustration (diagram, flat vector, infographic, isometric, cartoon) - or let the AI pick per scene
- Finds YouTube clips and downloads only the seconds it needs
- AI images and AI videos (OpenAI, Gemini, Higgsfield, any OpenAI-compatible API, MCP servers)
- Automatic fail-over: if one AI service fails, the next one takes over instantly
- Live activity log, cost tracking per service, one-click Stop

**Result:** only one part of the script was selected - the clips were found, trimmed and placed on the
timeline in order, each one starting exactly when its words are spoken.

<p align="center">
  <img src="images/timeline.png" alt="B-roll clips placed on the After Effects timeline" width="860">
</p>

### Text
- Subtitles (full lines or single lines), word-by-word captions, animated key phrases
- 13 text animations, any installed font, Bangla support

### Edit layer
- **Change with AI** - describe a change, the image layer is replaced in place
- **Remove background** - free, runs on the computer
- **Blur faces** - mosaic over every face in an image or video, with tracking (privacy)

### Lines - node board for connecting-line animations

<p align="center">
  <img src="images/lines-board.png" alt="Lines node board" width="480">
</p>

- Select layers and see them on a board over the real comp frame
- Drag a rope from one layer to another to connect them; Hub and Chain presets
- Styles: straight, curved, elbow, zigzag, wavy, dashed - with colour, width, taper and wave controls
- Direction: from A to B, from B to A, or from the middle out
- Creates shape layers with Trim Paths keyframes that follow the layers when they move

---

## How it works

```
Script + Voiceover
       |
       v
 Speech-to-text with word timings  -->  every script line gets its exact time
       |
       v
 AI planning  -->  per scene: video or image? which style? what to search / draw?
       |
       +--> YouTube search + download of only the needed seconds
       +--> AI image / AI video generation (with automatic fail-over between services)
       |
       v
 After Effects panel places everything on the timeline at the playhead
```

---

## Tech stack

| Part | Technology |
|---|---|
| After Effects panel | ExtendScript (Adobe JavaScript), ScriptUI, AE expressions |
| Engine | Python 3 |
| Speech-to-text | faster-whisper, OpenAI Whisper API |
| AI | Claude, Gemini, OpenAI, OpenAI-compatible APIs, Higgsfield, MCP |
| Video | yt-dlp, ffmpeg |
| On-device AI | ISNet background removal (onnxruntime / OpenCV), YuNet face detection |
| Installer | PowerShell one-click installer |

About 5,900 lines of code across Python, ExtendScript and PowerShell.

---

## My role

- Defined the problem from my own editing work and designed the workflow inside After Effects
- Specified every feature, tested each version on real projects and reported what to fix
- Directed the AI coding assistant through many iterations, from first prototype to installer
- Designed the user experience: tabs, presets, the node board and the text animations

---

## Contact

**Bayzid Ahmad** - video editor & motion designer
Upwork: YOUR-UPWORK-LINK
