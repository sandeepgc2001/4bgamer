# 4B Gamers Official Website

Static website for **4B Gamers Official**, designed for GitHub Pages.

## Pages

- `index.html` — main gaming/community website
- `nerp.html` — Nepal Elite Roleplay page
- `silent-warriors.html` — Silent Warriors [NPL] PUBG PC community page
- `css/main.css` — shared site styles
- `media/` — images, icons, and game/community artwork

## Run locally

No build step is required. Open `index.html` directly, or serve the folder with a simple static server, for example:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

## Deployment

The repository contains `.github/workflows/static.yml` for GitHub Pages deployment.

## Notes

- The YouTube section uses the channel's public uploads playlist, so no YouTube API key is exposed in the browser.
- The TikTok section reads the configured RSS feed in the browser. It will show a friendly fallback message if the RSS provider blocks cross-origin browser requests.
- The contact form is client-side only. To deliver messages, connect a static-form provider or backend endpoint and update the form handler.
- Social media icons are intentionally disabled until real profile URLs are configured.

## Security

Never place private API keys or secrets in HTML/JavaScript committed to a public repository. Browser code is visible to every visitor.

## 2026 community update

The site now includes a stronger landing-page CTA, responsive navigation, community highlights, community server status labels, events, community and team sections, an upgraded footer, back-to-top control, Open Graph metadata, a branded 404 page, and basic PWA/offline support (`manifest.webmanifest` + `sw.js`).

All features remain compatible with GitHub Pages. Items marked **TBA** or **Coming Soon** intentionally avoid inventing Discord invite URLs or event dates that were not included in the source project.


## Multi-platform Live Hub

The homepage includes a live hub for YouTube, Kick, Twitch, TikTok and Facebook.
Configure public channel information in `live-config.js`.

- **YouTube:** channel ID is already configured.
- **Kick:** add your public Kick username and channel URL. Kick supports iframe livestream embeds.
- **Twitch:** add your public Twitch username and URL. Twitch requires the current HTTPS domain as the `parent` parameter; the site calculates this automatically on GitHub Pages.
- **TikTok:** add your public LIVE/profile URL. The site opens TikTok in a new tab; latest TikTok clips remain embedded below.
- **Facebook:** add your public Facebook page URL. For an inline live player, set `liveVideoUrl` to the exact public Facebook Live video URL while broadcasting.

**Never put OBS stream keys, passwords, API secrets, or access tokens in `live-config.js` or any GitHub Pages file.**

## Automatic live players

The Live Hub is configured for automatic channel playback on GitHub Pages:

- YouTube: uses the configured channel ID and YouTube live channel embed.
- Twitch: uses the configured channel username and Twitch channel player.
- Kick: uses the configured channel username and Kick channel player.
- The active native player refreshes every 2 minutes and again when a visitor returns to the browser tab.

The default Twitch/Kick username is `4bgamersofficial`. If your real handle is different, change only `live-config.js`.

TikTok and Facebook do not offer the same simple public channel-live iframe/status flow for a static GitHub Pages site, so those remain profile/live-link based unless an external backend/API is added.

Never add OBS stream keys, passwords, client secrets, or API tokens to `live-config.js` or any GitHub Pages JavaScript file.


## Silent Warriors [NPL]

A dedicated responsive showcase page is available at `silent-warriors.html`. It uses the existing local `media/dcimage/npl.png` artwork as a reliable fallback and also references the Discord CDN artwork supplied by the site owner. The Silent Warriors Discord invite remains intentionally unconfigured until a confirmed public invite is provided.
