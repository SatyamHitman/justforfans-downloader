# JustForFans Downloader — Browser Extension for Chrome, Brave & Edge

Save the JustForFans photos and videos you already pay for, **at full quality**, processed entirely on your own device.

This is the JustForFans documentation for [**Fanripper**](https://fanripper.com) — a browser extension that also supports OnlyFans, Fansly and privacy.com.br.

⬇️ **[Install](https://install.fanripper.com)** &nbsp;·&nbsp; 🌐 **[JustForFans downloader page](https://fanripper.com/justforfans-downloader)** &nbsp;·&nbsp; 💬 **[Telegram](https://t.me/fanripper)**

---

## The 720p problem, and why it isn't real

This is the part worth understanding, because it is the single biggest quality difference between tools.

JustForFans encrypts a large share of its video. Many downloaders see encryption and assume **Widevine** — the heavyweight DRM OnlyFans uses, which needs a licence server and a content decryption module. Faced with that, a tool either refuses the video or falls back to whatever unencrypted rendition it can find, which is usually **720p or a preview**.

JustForFans does not use Widevine. It uses **ClearKey with `cbcs` (AES-CBC pattern) encryption**, where the key is fetched over an ordinary signed HTTPS request. That is a fundamentally lighter scheme, and it means the *full* rendition ladder is reachable.

Fanripper decrypts `cbcs` locally, in your browser, and takes the **top rendition the creator actually uploaded** — 1080p where JustForFans has it. There is no cap on our side.

The decryption key is fetched **directly from the CDN by your own browser**, cookie-less. It never passes through our servers, so we hold no record of what you downloaded.

## What it saves

| | |
|---|---|
| **Encrypted video** | Decrypted locally, top rendition, no 720p ceiling |
| **Photos** | The original file — JustForFans serves resized copies through an image CDN, and Fanripper unwraps that to the original underneath |
| **A whole profile** | Walks the feed page by page at a human rhythm |
| **Your entire library** | Every purchased and private item, across **every creator you have ever bought from**, in one run — not one profile at a time |
| **DMs** | Photos and unencrypted clips (see the limits below) |
| **Quality picker** | On a single video, choose any rendition the manifest carries |

## Honest limits

Stated here rather than discovered later:

- **Encrypted video sent in a DM cannot be saved yet.** DM photos and unencrypted DM clips work. A fix is in progress.
- **No story downloads.**
- **Bulk runs take the top quality**, not a rung you picked — the picker applies to single videos.
- **Date and paid-only filters apply to your library backup, not to a whole-profile feed run** — feed posts do not carry the dates to filter on. Media-type filtering works on both.
- **A whole-profile run does not carry the original post date or caption** into the file, because the JustForFans feed does not expose them.
- It **does not bypass a paywall**. Only content your account can already open.

## Regional CDNs — the "works for everyone else but not me" bug

JustForFans serves video from regional CDNs. A downloader that only recognises a handful of hosts works fine for the developer and fails for users on other continents — which is exactly the bug Fanripper shipped a fix for in 0.1.54. It now accepts the whole regional fleet, so a US, Asian or VPN connection behaves the same as a European one.

If you still hit region-specific failures, [Telegram](https://t.me/fanripper) is the fastest route to a fix.

## Install (about 60 seconds)

1. Download `fanripper.zip` from [install.fanripper.com](https://install.fanripper.com).
2. Unzip it somewhere permanent.
3. Open `chrome://extensions` and turn on **Developer mode**.
4. Click **Load unpacked** and pick the unzipped folder.
5. Open JustForFans — a save button appears on content you can already see.

Works on Chrome, Brave and Edge. It is not in the Chrome Web Store because stores remove extensions that work with subscription content.

**Updating:** a load-unpacked install cannot update itself. Fanripper tells you when a new version ships; extract it over the same folder and hit **Reload** — about 15 seconds, and your settings and login are kept.

## Which plan

JustForFans is on **Max** ($15/month) or **Lifetime** ($99 once), alongside privacy.com.br. The Free, Basic, Pro and Unlimited plans cover OnlyFans and Fansly. Paid plans are bought inside the extension in crypto or Telegram Stars — no card, no KYC.

## Is it safe?

- Runs entirely in your browser. Media and your login session never reach our servers.
- **Never asks for your JustForFans password** — it works through the session you are already signed into. Anything asking you to type your platform password into it is a credential grab, not a downloader.
- Paces requests like ordinary browsing rather than hammering the site.
- The shipped build is flagged by **0 of 65** engines on VirusTotal.

No tool that talks to a site it does not control can promise you an outcome, and anything claiming "100% undetectable" is bluffing. Local processing, no password, and human-paced requests are the honest version.

## Links

- 🌐 [fanripper.com](https://fanripper.com) — all four supported sites
- 📊 [Side-by-side capability comparison](https://fanripper.com/supported-sites)
- 📖 [JustForFans guide](https://fanripper.com/blog/justforfans-video-downloader-chrome)
- 💬 [Telegram](https://t.me/fanripper)

## Disclaimer

Fanripper is a personal backup utility for content you have **lawful, paid access to**. It is **not affiliated with, endorsed by, or connected to** JustForFans or any content platform. No paywall is bypassed. You are responsible for complying with the platform's terms of service and your local law.
