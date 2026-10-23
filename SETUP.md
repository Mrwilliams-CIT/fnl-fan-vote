# Friday Night Lights Fan Vote: Setup

The whole kiosk is one file, `index.html`. The logos are built into it, so it doesn't need any other files.

## 1. Host the page

OptiSigns needs a URL. Use the same steps as Fright Night:
1. Drag the `friday-night-lights-vote` folder onto **app.netlify.com/drop**.
2. You'll get a link like `https://something.netlify.app`.

If an uploader asks for a zip (like OptiSigns' HTML5 content), use `friday-night-lights-vote.zip`.

## 2. OptiSigns

1. Add a **Website** app that points at the Netlify link.
2. Set the screen to **portrait**.
3. Tap-test the real screen to make sure touches reach the page.
4. Turn off OptiSigns' auto-refresh, or set it to a long interval. A refresh won't erase votes, but it does interrupt students.

## How votes are saved

- Votes are saved **in the screen's browser only**. A reload or a reboot keeps them.
- Clearing that browser's data, or switching to a different player or browser, starts the count over.
- Votes from a test on your laptop stay on your laptop. They don't show up on the kiosk.

## Staff tools

Hold the **top-left corner** of the screen for 3 seconds, then enter the PIN (**1031**).
- **Results:** shows each game's vote counts.
- **Reset all votes:** tap it twice to confirm.

To change the PIN, edit `ADMIN_PIN` in the SETTINGS block near the top of `index.html`.

## Built-in safeguards

- After each vote, that game pauses for 2 seconds and shows "VOTE COUNTED!" Taps faster than a quarter second apart are ignored on every game.
- Pinch zoom, double-tap zoom, and right-click menus are turned off.
- If nobody taps for 20 seconds, random logos bounce with a "TAP ME!" hint.
- Every 50 total votes, a big celebration banner appears.

## Next week

Open `index.html` in a text editor and change the **SETTINGS** block near the top:
- `WEEK`. A new week number starts a fresh set of votes.
- Each game's `when`, `name`, `rec` (record), and `color`.
- `home: true` puts a HOMETOWN tag on that team.

Teams already in the `LOGOS` list at the bottom of the file can be reused. A brand new opponent needs its logo added.

The title art and scenery come from the weekly preview poster, which is built into the page. It still says "Week 10 Preview" and the October 23-24 dates. Each week, send Claude the new poster so the background, title, and logos all match.

## Try it

Open `index.html` in a browser. Add `?seed` to the end of the URL to fill it with random practice votes. Use the staff panel to reset them afterward.
