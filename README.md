# Piano Starter

A single-page piano lesson app for kids and adult beginners. No build step, no dependencies: open `index.html` in a browser.

## Features

- Two-octave on-screen keyboard (C4 to C6) with Web Audio sound. On phones it shows about ten white keys with Lower/Higher buttons; on tablets and wide screens (700 px and up) both octaves fit with taller keys and no scrolling
- Kids and Adults modes (different look, wording, and rewards)
- Grouped lesson list: first notes, songs, chords, chords + melody, and two-hand lessons
- Chords and two-hand steps: press every glowing key within about two seconds
- Star ratings per lesson, based on missed notes

## Run it

Open `index.html` in any modern browser, including Safari on iPhone and iPad.

## Host it free with GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repo, go to Settings, then Pages.
3. Under "Build and deployment", choose "Deploy from a branch", pick `main` and the `/ (root)` folder, and save.
4. After a minute, the app is live at `https://<your-username>.github.io/<repo-name>/`.

## Notes

- Fonts load from Google Fonts; the app falls back to standard fonts when offline.
- Song melodies were entered by hand. "Saints Go Marching" and "Amazing Grace" cover only the opening phrases. Check them against a trusted score before teaching from them.
- Progress (stars, last lesson, Kids/Adults mode) is saved in the browser with localStorage. The lesson list has a Reset progress item.
- Rhythm mode: a metronome with a four-beat count-in, three tempos (50, 70, 90 BPM), and "On beat", "Early", or "Late" feedback on every note, with a timing summary at the end.
- "Hear it" plays the lesson while the keys light up. Finger numbers appear on lessons that fit one hand position (C to G).

## Adding lessons

Lessons live in the `LESSONS` array in `index.html`. Each lesson has a title (`t`), a list of steps (`s`), and text for kids and adults. A step is a note number (0 = middle C, counting in semitones) or a list of numbers for keys pressed together. Lesson groups in the list are set by the `GROUPS` array, using each group's starting position.
