# Friday Night Lights Fan Vote: Setup

The whole kiosk is one file, `index.html`. The poster art, logos, and scare pictures are built into it.

## Where it lives

- Live page: **https://mrwilliams-cit.github.io/fnl-fan-vote/**
- Code: https://github.com/Mrwilliams-CIT/fnl-fan-vote

In OptiSigns, use a **Website** app pointed at the live page, set to portrait. When the page is updated on GitHub, the screen picks up the change the next time it reloads. You don't need to change anything in OptiSigns.

Turn off OptiSigns' auto-refresh, or set it to a long interval. A refresh won't erase votes, but it does interrupt students.

## How votes are saved

- Votes are saved **in the screen's browser only**. A reload or a reboot keeps them.
- Clearing that browser's data, or switching to a different player or browser, starts the count over.
- Votes cast on a laptop or phone stay on that device. They don't show up on the kiosk.
- A new week number starts a fresh count.

## Staff tools

Hold the **top-left corner** of the screen with one finger for 3 seconds, then enter the PIN (**1031**).
- Use one finger and keep it still. Two fingers, a palm, or sliding off the corner cancels the hold.
- 3 wrong PINs in a row lock the corner for 5 minutes.
- The panel closes by itself after 1 minute without a tap.
- **Results:** shows each game's votes, Salem cheers, and students scared.
- **Scares ON/OFF:** turns jump scares on or off. **OFF makes it a plain fan poll**: the "Students Scared" box goes away, the banner changes to "Tap a team to vote!", and the scare buttons are hidden.
- **Sound ON/OFF:** quiet mode. The scare still shows, with no scream.
- **Volume:** tap to cycle through 25%, 50%, 80%, and 100%.
- **Rare / Normal / Often:** how often scares happen (see below).
- **Test scare:** runs a scare right away so you can check the picture and sound. It doesn't count toward "Students Scared."
- **Reset all votes:** tap it twice within 5 seconds to confirm.

These settings are saved on the screen and stay set from week to week.

## How the jump scare works

- Each new person gets a secret random tap number. When they reach it, the zombie or the scarecrow lunges out with no warning and screams. Next comes a "GOTCHA! Happy Halloween!" screen, and their vote still counts.
- Each person gets scared only once. After 8 seconds with no taps, the next tap counts as a new person. Once the wait time has passed, a steady crowd can get scared again.
- How often:
  - **Rare:** on tap 5 to 10, at most once every 5 minutes.
  - **Normal:** on tap 3 to 8, at most once every 2 minutes.
  - **Often:** on tap 2 to 5, at most once every 45 seconds.
- The two pictures take turns.
- The scream is a recording from Pixabay (free to use), built into the page. If it can't play, a scream made in code plays instead.
- The flicker stays under 3 flashes per second.

**Check the sound on the real screen.** Some OptiSigns players mute website audio. Use **Test scare**. Browsers only allow sound after someone touches the screen, and the PIN taps count.

## Built-in safeguards

- After each vote, that game pauses for 2 seconds and shows "VOTE COUNTED!" The Salem cheer button pauses for about 1 second.
- Taps faster than a quarter second apart are ignored.
- Taps are ignored during a scare. A safety timer means the screen can never get stuck on a scare.
- The 6-hour refresh only happens if the site is reachable, so a network hiccup can't leave an error page.
- If the screen can't save votes, the staff panel shows a warning.
- Pinch zoom, double-tap zoom, and right-click menus are turned off.
- If nobody taps for 20 seconds, random logos bounce with a "TAP ME!" hint.

## Next week

Send Claude the new preview poster. The background, title, matchups, and logos all come from it.

To change something small yourself, edit the **SETTINGS** block near the top of `index.html`:
- `WEEK`, and each game's names, records, seeds, colors, and times.
- `CHEER` is the "Cheer for..." card for a team with a bye. Set it to `null` to hide it.
- `SCARES` holds the scare defaults for a screen that has never been changed in the staff panel.

## Try it

Open the live page in a browser. Add `?seed` to the end of the URL to fill it with random practice votes. Use the staff panel to reset them afterward.
