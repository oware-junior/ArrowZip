# Arrow Zip

![Arrow Zip](screenshots/feature_graphic.png)

A relaxing arrow puzzle game for Android, built with Flutter.

Tap an arrow and it slides out of the board along its own path. If another
arrow is in the way, it bumps and you lose a heart. Clear the whole board to
win. Currently in closed testing on Google Play.

<p>
  <img src="screenshots/phone_1_gameplay.png" width="200" alt="Gameplay">
  <img src="screenshots/phone_2_blocked.png" width="200" alt="Blocked arrow">
  <img src="screenshots/phone_4_win.png" width="200" alt="Win screen">
  <img src="screenshots/phone_6_achievements.png" width="200" alt="Achievements">
</p>

## Features

- Endless levels: every level number makes a new board
- Over 5,000 different board shapes: 45 hand-drawn objects (rockets, cats,
  castles, owls, guitars...), letters and numbers, faces, stamps, cut-outs,
  flowers and gears, stars, polygons, pairs and patterns
- A hard level every fifth level: a bigger board packed with many more arrows
- Snake-shaped arrows that bend and slide out along their path
- Every level is solvable by construction
- Level clock with best times, star ratings and combos
- Hints, three hearts per level, and a step-by-step tutorial
- Daily challenge with streaks
- 40 achievements
- Light and dark themes, phone and tablet layouts
- Out of hearts? Try again for free, or watch an optional ad to keep your
  progress
- Optional sign-in (Google or email) and an ad-free subscription
- Tells players when an update is ready, and updates in place

## How the levels are made

Levels are not hand-made. The generator builds each board in reverse: it
starts from an empty board and places arrows one at a time so that each new
arrow can already slide out along its path. Removing them in the reverse order
of placement always clears the board, so every level has at least one
solution. It fills the board from the centre outwards, places long arrows
first and then fills the gaps, which keeps boards dense (about 90%). The level
number seeds the random generator, so the same level always looks the same.

## How the shapes work

Each board is cut to a silhouette. A few dozen shapes are drawn by hand: 19
geometric classics and 45 pixel-art objects. The rest are generated from
families: regular polygons and stars, flowers and gears from the Gielis
superformula, a bold 5x7 font for letters and numbers, and combinations such
as a shape with another shape or letter cut out of it, faces, stamps and
stacked pairs. Of 6,493 shapes, 5,167 give genuinely different boards (a test
checks this). Levels rotate through the families, and each family uses every
one of its shapes before any repeats, so neighbouring levels never look alike.
Shapes too thin to hold arrows are filtered out, measured on a background
isolate at startup.

## Tech

- Flutter and Dart, with Riverpod for state
- `CustomPainter` for the board, with slide, bump and hint animations
- Firebase Authentication (Google and email sign-in)
- Google Mobile Ads with UMP consent (banner, interstitial and rewarded),
  and `in_app_purchase` for subscriptions
- Google Play in-app updates
- Automated tests for the game rules, level solvability and UI
- Play Store screenshots rendered from the real widgets in a Flutter test

## Source code

The source code is private. If you're a recruiter or would like to see parts
of it, get in touch.

## Links

- [Portfolio](https://oware-junior.github.io/portfolio/)
- [LinkedIn](https://www.linkedin.com/in/oware-junior-544099414)
- [Privacy policy](https://oware-junior.github.io/arrow-policy/)

## Author

Made by Oware Junior (Junior Kofi Studios), a student at Ghana Communication
Technology University.

Copyright (c) 2026 Oware Junior. All rights reserved.
