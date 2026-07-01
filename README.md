# 🏋️ Gym Coach

A voice-guided workout website that runs entirely in your browser — no app, no account, no server.

Open it on your phone at the gym and it:

- **Knows when you're at the gym** — tap "📍 set gym" once at your gym to save the location. Next time you open the page there, it greets you and offers to start your workout.
- **Tells you what to do** — a voice coach announces each exercise ("Next up: Squats — 3 sets of 12"), with a quick form tip. It auto-picks the most natural voice on your device (Neural/Natural voices), and you can choose a different one in Coach settings. The lines are varied and hype — no robotic script.
- **Counts your reps out loud** — pick your pace (2–4 seconds per rep) and it counts every rep (or every 5th, or silently on screen).
- **Use your own voice** — record yourself saying each coach phrase (numbers, "Go!", "Switch legs!", "Set done — take a break!"…) via 🎙 Record in Coach settings, and the coach speaks in *your* voice. Clips are stored on-device (IndexedDB); anything you skip falls back to the phone voice.
- **Voice packs** — export all your clips as one `voicepack.json` file and import it on another device, or commit that file to this repo next to `index.html`: the site then auto-loads your voice on every device that opens it (local recordings still take priority).
- **Tells you when to rest** — automatic rest timers between sets, with a "10 seconds left" heads-up.
- **Plays music during sets** — four options:
  - **🟢 My Spotify** — paste any Spotify playlist/album/song link once and it plays through the official Spotify embed. Full songs when you're logged in to Spotify in the browser (previews otherwise). The coach pauses/resumes it around announcements (Spotify's embed has no volume control).
  - **🦉 Drake mix** — streams a built-in Drake playlist through the official YouTube embed player (needs internet). You can also paste any YouTube song or playlist link instead.
  - **Your own songs** — pick MP3s from your phone; plays offline.
  - **Built-in beat** — a generated 128 BPM workout beat, works anywhere.

  For YouTube, own songs, and the beat, the music automatically ducks down whenever the coach speaks, then comes back.
- **Tells you when to move on** — "Great job, Squats done! Move on to Leg Press."
- **Remembers your workouts** — recent sessions are saved on your device.

## Built-in programs

- **Full Body** — squats, push-ups, lat pulldown, shoulder press, plank
- **Push Day** — bench, incline press, shoulder press, lateral raises, pushdowns
- **Pull Day** — pulldown, rows, face pulls, curls
- **Glute Day** — glute bridge activation, hip thrusts, RDLs, Bulgarian split squats (per-leg with a "switch legs" callout), leg press (high & wide stance), hip abductors, cable kickbacks, calf press

Programs live in the `PROGRAMS` object at the top of the script in `index.html` — edit names, sets, reps, and rest times to make them yours.

## How to use it

It's a single `index.html` file. Easiest way to get it on your phone:

1. **GitHub Pages (recommended):** in this repo go to *Settings → Pages*, set the source to your branch, and GitHub gives you a URL like `https://<user>.github.io/gym/`. Bookmark it on your phone's home screen.
2. Or open the file directly in any browser.

> **Note:** the gym-location feature needs HTTPS (GitHub Pages provides it) and location permission. Voice uses your browser's built-in speech — the first "Start workout" tap enables audio.

Everything (gym location, history, settings) is stored in your browser's localStorage — nothing leaves your device.

## 💌 `foryou.html` — a personal page with your voice

A separate little page (`foryou.html`) you can personalize and send to someone special. Open it, tap **✎ Personalize**, and you can:

- **Record your voice** right in the browser — it becomes a "press play, I recorded this for you" button at the top.
- Edit all the words: their name, the reasons, your letter, an optional Spotify song, and a reply button (e.g. `sms:` or `mailto:`).
- Tap **⬇ Download my page** to get a single `for-you.html` file with your voice and words **baked inside it** — send that file to them (or upload it to the repo for a link) and they'll hear you on any device. No account, no server; the audio rides along inside the HTML.

> Recording needs microphone permission, and the "Download my page" step works when the page is opened via its web link (not a file opened directly from disk).
