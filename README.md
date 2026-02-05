# Mux Minutes Delivered Calculator

A visual tool to understand how Mux bills for video delivery. Watch in real-time as video segments are downloaded and see exactly how "minutes delivered" accumulates.

## Live Demo

**[View Live Demo](https://YOUR_USERNAME.github.io/mux-player-minutes/)**

## Features

- Real-time tracking of minutes delivered (Mux's primary billing metric)
- Visual breakdown of bandwidth by quality level
- Minutes breakdown by quality level
- Cache detection (cached segments don't count toward billing)
- Segment download log
- Support for signed URLs (playback tokens)
- Works with on-demand, live, and low-latency live streams

## How It Works

Mux bills based on **minutes delivered** — the total duration of video segments sent from the CDN to the player. This tool hooks into the HLS.js player inside Mux Player to track every segment download and calculate the billing-relevant metrics.

Key insights:
- A 10-second segment at 1080p costs the same as 10 seconds at 480p
- Seeking can cause additional segments to be downloaded
- Quality switches may re-download segments at the new bitrate
- Browser-cached segments don't count toward billing (they were already billed)

## Deploy to GitHub Pages

1. Fork or clone this repository
2. Go to your repo Settings → Pages
3. Under "Source", select "Deploy from a branch"
4. Select `main` branch and `/ (root)` folder
5. Click Save

Your site will be live at `https://YOUR_USERNAME.github.io/mux-player-minutes/`

## Local Development

Just open `index.html` in your browser, or serve with any static file server:

```bash
# Python
python -m http.server 8000

# Node.js
npx serve .
```

## Usage

1. Enter a Mux playback ID
2. (Optional) Add signed URL tokens if the video is protected
3. Click "Load Player"
4. Play the video and watch the metrics update in real-time

## Built With

- [Mux Player](https://docs.mux.com/guides/mux-player-web) - The official Mux video player
- Vanilla HTML/CSS/JavaScript - No build step required

## Learn More

- [Mux Delivery Billing Docs](https://docs.mux.com/guides/video/track-delivery)
- [Understanding Minutes Delivered](https://www.mux.com/blog/understanding-video-delivery-minutes)
