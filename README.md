# Piano Starter

A single-page piano lesson app for kids and adult beginners. No build step, no dependencies: open `index.html` in a browser.

## Features

- Two-octave on-screen keyboard (C4 to C6) with Web Audio sound. On phones it shows about ten white keys with Lower/Higher buttons; on tablets and wide screens (700 px and up) both octaves fit with taller keys and no scrolling
- Kids and Adults modes (different look, wording, and rewards)
- Grouped lesson list: first notes, songs, black keys, chords, chords + melody, two-hand lessons, and advanced modes (Ionian, Dorian, Phrygian, Lydian, Mixolydian, Aeolian, Locrian)
- Chords and two-hand steps: press every glowing key within about two seconds
- Star ratings per lesson, based on missed notes

## Install and offline use

When served from GitHub Pages (https), the app can be added to the home screen and works without internet after the first visit.

- **iPhone or iPad (Safari):** tap Share, then Add to Home Screen.
- **Android (Chrome):** open the menu, then Install app or Add to Home screen.
- **Desktop Chrome or Edge:** use the install icon in the address bar.

Keep these files together in the repo root: `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, and `apple-touch-icon.png`. The service worker loads fresh files whenever you are online and falls back to its saved copy when you are not, so updates arrive on the next visit with internet. If you ever rename or add files that the app needs offline, add them to the `FILES` list in `sw.js` and change the `CACHE` name.

## Run it

Open `index.html` in any modern browser, including Safari on iPhone and iPad.

## Host it free with GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repo, go to Settings, then Pages.
3. Under "Build and deployment", choose "Deploy from a branch", pick `main` and the `/ (root)` folder, and save.
4. After a minute, the app is live at `https://<your-username>.github.io/<repo-name>/`.

## Notes

- Fonts load from Google Fonts; the app falls back to standard fonts when offline.
- Song melodies were entered by hand. "Saints Go Marching", "Amazing Grace", "Itsy Bitsy Spider", "Silent Night", "Greensleeves", and "Old MacDonald" cover only the opening phrases. Check them against a trusted score before teaching from them.
- Progress (stars, last lesson, Kids/Adults mode) is saved in the browser with localStorage. The lesson list has a Reset progress item.
- Rhythm mode: a metronome with a four-beat count-in, three tempos (50, 70, 90 BPM), and "On beat", "Early", or "Late" feedback on every note, with a timing summary at the end.
- Music theory: ten short topics (half and whole steps, the major scale pattern, intervals, triads, chords in a key, inversions, relative minor, circle of fifths, note values and time signatures, chord symbols). Most have a Play example button that lights the keys and plays the notes. Kids mode uses simpler wording.
- Chord library: pick any of 12 roots and a chord type (major, minor, diminished, augmented, sus2, sus4, major 7, minor 7, dominant 7). The keys light up, the chord plays, and notes are spelled correctly (for example E major is E G♯ B). Kids mode shows major, minor, and dominant 7 with a mood word.
- Read the staff: a treble-clef note appears and you tap the matching key. Ten notes per round, three levels (C to G, C to C, all keys), scored on first-try accuracy. The clef symbol is a Unicode character, so it depends on the fonts on the device.
- Mode ear quiz: five questions. The app plays a scale starting on C and you pick the mode (Kids mode uses four moods: happy, sad, dark, dreamy; Adults mode uses all seven modes). The keys still make sound during the quiz.
- "Hear it" plays the lesson while the keys light up. Finger numbers appear on lessons that fit one hand position (C to G).

## Adding lessons

Lessons live in the `LESSONS` array in `index.html`. Each lesson has a title (`t`), a list of steps (`s`), and text for kids and adults. A step is a note number (0 = middle C, counting in semitones) or a list of numbers for keys pressed together. Lesson groups in the list are set by the `GROUPS` array, using each group's starting position.
