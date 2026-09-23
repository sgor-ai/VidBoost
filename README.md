<div align="center">

# VidBoost

**A compact glassmorphism HUD for boosting video volume and controlling playback speed.**

[Created by **sgor-ai**](https://github.com/sgor-ai)

[![Userscript](https://img.shields.io/badge/Tampermonkey-userscript-00485B?logo=tampermonkey&logoColor=white)](https://www.tampermonkey.net/)
[![Version](https://img.shields.io/badge/version-1.0.0-2563eb)](https://github.com/sgor-ai/VidBoost)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

</div>

<p align="center">
  <img src="docs/media/vidboost-demo.gif" alt="VidBoost volume and speed controls" width="860">
</p>

<p align="center"><strong>Press <code>Alt</code> + <code>Shift</code>, tune the video, and keep watching.</strong></p>

## What is VidBoost?

VidBoost is a lightweight [Tampermonkey](https://www.tampermonkey.net/) userscript
that adds a small, unobtrusive control panel to webpages containing HTML5 video.
It uses the same dark, translucent glass panel for every site and keeps the
controls close to the active video.

The panel provides:

- **Volume boost** from `0%` to `1000%` using the Web Audio API.
- **Playback speed** from `0.5x` to `4.0x`.
- A live green, amber, and red volume indicator.
- A keyboard toggle with **Alt + Shift**.
- Automatic selection of the currently playing video.
- Support for pages with multiple video elements.

> VidBoost changes playback in your browser only. It does not download,
> re-encode, or upload videos.

## Demo

The supplied demo shows the VidBoost panel and its controls in the same
glassmorphism style used by the userscript:

![VidBoost demo](docs/media/vidboost-demo.gif)

## Install by copying the script

1. Install the [Tampermonkey browser extension](https://www.tampermonkey.net/).
2. Open the [raw userscript](https://raw.githubusercontent.com/sgor-ai/VidBoost/master/vidboost.user.js).
3. Copy the entire file with **Ctrl+A**, then **Ctrl+C**.
4. Open the Tampermonkey dashboard and choose **Create a new script**.
5. Replace the starter template with the copied text.
6. Press **Ctrl+S** or choose **File > Save**.
7. Open a page containing an HTML5 video and press **Alt + Shift**.

The userscript matches all webpages by default so it also works on video
players embedded in sites that do not expose their own volume boost control.

You can also open [`vidboost.user.js`](vidboost.user.js), copy its contents,
and paste them directly into a new Tampermonkey script. This project is only
a text userscript: there is no installer, build step, or release download.

## Usage

### Open and close the HUD

Press **Alt + Shift** together. The panel appears in the top-right corner of
the active video. Press the same shortcut again to hide it.

### Volume

Drag **Volume** to set the gain:

| Range | Indicator |
| --- | --- |
| `0%` - `400%` | Green |
| `400%` - `700%` | Amber |
| `700%` - `1000%` | Red |

The value is intentionally shown as a percentage of normal volume. For
example, `250%` means approximately 2.5x gain.

### Speed

Drag **Speed** from `0.5x` for slow playback to `4.0x` for fast playback.
The value is applied to the active video immediately.

## Compatibility and limitations

- Works in modern Chromium, Firefox, and other browsers supported by
  Tampermonkey.
- Requires a page with at least one HTML5 `<video>` element.
- The active video is the first playing video, or the first video found when
  nothing is currently playing.
- Browser autoplay policies can keep the Web Audio context suspended until the
  first user interaction.
- Some protected or custom players may restrict media-element audio routing.

## Privacy

VidBoost has no network requests, no telemetry, no storage, and no external
dependencies. It only reads video elements on the current page and modifies
their local audio gain and playback rate.

## Project layout

```text
vidboost.user.js        Tampermonkey userscript
docs/media/
  vidboost-demo.gif     Supplied controls demonstration
LICENSE                 MIT license
README.md               Documentation
```

## Development

The userscript is intentionally self-contained. To work on it:

1. Edit `vidboost.user.js`.
2. Save it in Tampermonkey or reload the script from the dashboard.
3. Refresh the video page.
4. Press **Alt + Shift** and test both sliders.

No build step is required.

## Responsible use

Use VidBoost for videos you are allowed to watch and modify locally. Respect
the terms of service, accessibility needs, and volume limits of the websites
you use. High gain can damage hearing or speakers; start at a low value.

## License

VidBoost is released under the [MIT License](LICENSE).
