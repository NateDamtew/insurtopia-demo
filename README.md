# insurtopia-demo

Interactive concept demos for **InsurEthiopia** — an insurance experience presented as a
telebirr mini-app.

## Demos

| | |
|---|---|
| [`index.html`](index.html) | **telebirr mini-app concept.** The telebirr home screen with an InsurEthiopia tile in place of "Transfer to Bank". Tapping it slides the live app up as a mini-app. |
| [`standalone.html`](standalone.html) | The live app on its own, inside a switchable iPhone frame with a screen-jump menu. |

Both are single self-contained HTML files. Open them directly, or view the hosted versions.

## On a phone

Open the link on a phone and the device frame is dropped — the screenshot fills the
screen, so it simply looks like the app. The toolbar is replaced by a small **⋯** button
in the corner (back to home, reload, highlight toggle, open app in a new tab).

The screen is letterboxed to the screenshot's 414×896 aspect, which keeps the tile
aligned on any handset. On iOS you can also **Share → Add to Home Screen** to launch it
without browser chrome.

> **iOS note:** Safari blocks storage for sites embedded in a frame, so signing in to the
> app *inside* the mini-app view may fail on iPhone. Use **⋯ → Open app in new tab**,
> which loads it first-party where sign-in works normally. On Android Chrome the embedded
> sign-in works as-is.

## Using them in a pitch

- **`P`** — present mode, hides every control so only the phone is on screen
- **`Esc`** — close the mini-app / exit present mode
- **`R`** — reload the embedded app
- Turn off **Highlight tile** before you tap, so the pulsing ring doesn't distract

The embedded app loads as soon as the page opens, so the mini-app is already painted
by the time you tap the tile — no white flash in front of an audience.

Use **Chrome or Edge**. Safari's tracking prevention can drop the app's session inside a
third-party iframe and sign you out mid-demo.

## How the tile is placed

The home screen is a real telebirr screenshot (iPhone XR/11, 828×1792 @2×). The replacement
tile is an HTML card positioned over the original "Transfer to Bank" cell, using measurements
taken from the image itself:

- grid columns at x = 24 / 225 / 426 / 627, cell width 177
- second row spans y = 845–1050
- corner radius ≈ 10px, label `#333`, telebirr green `#8DC63F`, badge `#FFC20E`

All at 2×, so the CSS box is `313.5, 422.5, 88.5 × 103`.

## Disclaimer

This is an **unofficial concept mockup**, built to illustrate a proposed integration.

It is **not affiliated with, endorsed by, or produced by Ethio Telecom or telebirr.** The
telebirr home screen appears here as a static screenshot for illustration only, and all
telebirr, Ethio Telecom, and partner-bank marks belong to their respective owners. Nothing
here is live telebirr functionality — the only working part is the InsurEthiopia app itself,
loaded from its own domain.
