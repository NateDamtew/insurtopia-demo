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

## The script

`index.html` runs as a stepped walkthrough. The left panel says what's on screen, the
right panel carries the talking points and the action to take, and the dots at the bottom
move between steps.

Each step can also drive the demo — open the mini-app, jump to a given screen — so the
notes and the phone stay in sync. The page can't read the app (different domain), so
steps *drive* it rather than follow it. If you'd rather tap through by hand, switch
**Sync screens** off and the steps become notes only.

**The copy is a starting point — rewrite it.** It lives in one array called `STEPS` near
the top of the `<script>` in `index.html`, with a comment explaining each field. Nothing
else needs touching to change the narrative.

> Because steps jump straight to app screens, **sign in once at the start**. The session
> is kept in `localStorage`, so every later step lands on a real screen instead of the
> login page.

## Using them in a pitch

- **`→` / `space`** — next step · **`←`** — previous · **`Home`** — back to step 1
- **`P`** — present mode: drops the toolbar but keeps the notes, step dots and logo
- **`Esc`** — close the mini-app / exit present mode
- **`R`** — reload the current screen
- **Notes** hides the side panels and gives the phone the full stage
- Turn off **Highlight tile** before you tap, so the pulsing ring doesn't distract

Panels need room, so they hide automatically below 1180px wide and on phones.

The embedded app loads as soon as the page opens, so the mini-app is already painted
by the time you tap the tile — no white flash in front of an audience.

The stage is styled in the D'Afrique brand teal `#1C4B42`, with the logo in the
bottom-right corner. Present mode keeps the logo and drops everything else, so a
projected screen shows just the phone on brand colour.

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
