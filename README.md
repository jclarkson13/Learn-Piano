# Piano Starter

A single-page piano lesson app for kids and adult beginners. No build step, no dependencies: open `index.html` in a browser.

## Features

- Full-width, responsive two-octave on-screen keyboard (C4 to C6) with Web Audio sound
- Responsive layout that reflows for narrow and wide browser windows
- Kids and Adults modes (different look, wording, and rewards)
- Lessons grouped by skill level: Beginner, Intermediate, and Advanced
- Music Theory path introducing treble-staff reading and intervals
- Circle of Fifths path for ascending fifths, key relationships, and signatures
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
- Progress is not saved between visits yet.

## Adding lessons

Piano lessons live in the `LESSONS` array in `index.html`. Each lesson has a title (`t`), a list of steps (`s`), and text for kids and adults. A step is a note number (0 = middle C, counting in semitones) or a list of numbers for keys pressed together. Music Theory lessons are defined in `THEORY_LESSONS`; `kind: 'staff'` exercises ask learners to read single notes, while `kind: 'interval'` exercises show note pairs and ask learners to play them in order. Circle of Fifths lessons are defined in `CIRCLE_LESSONS`.

The current Circle of Fifths path covers ascending fifths, clockwise/counterclockwise key movement, and signatures for C, G, D, F, and B-flat major.

## Planned Circle of Fifths lessons

- **Lesson 4: Relative major and minor.** Pair C major with A minor, G major with E minor, and F major with D minor. Explain that each pair shares a key signature, locate the relative minor three scale steps below its major, and let learners play both tonic triads.
- **Lesson 5: Chord progressions.** Use the circle to find neighboring I, IV, and V chords. Play I–IV–V–I in C (C–F–G–C), then G (G–C–D–G), and ask learners to identify the home chord. Add chord inversions only as an optional challenge.
