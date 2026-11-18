# Functional Spec — Sight Words Lucito

## Screens
1. **Home** — big icon buttons: Play Today, Dashboard, Test. Voice greets: "Hi Lucito! Ready to play?"
2. **Play** — one word per round. Screen shows 3-4 picture cards (one matches the word). Word is spoken. Lucito taps the matching picture. Correct: star + cheer sound + next round. Wrong: gentle "try again" voice, cards reshuffle.
3. **Dashboard** — grid of all 40 words. Color-coded: gray (not started), yellow (practicing), green (mastered, 3 correct in a row). Shows stars earned this week and accuracy %.
4. **Test** — 10 random words from current week. 4 picture options each, no hints beyond the spoken word. Score shown at end. 8/10 passes.

## Data Model (localStorage key: sightWordsLucito)
- words: { word, week, attempts, correct, streak, mastered }
- session: { date, wordsPlayed, correct }
- week: current week number (1-4)

## Audio
- Web Speech API, en-US, rate 0.85, pitch 1.1 (warm, slightly slow).
- Fallback: if speechSynthesis unavailable, show word text large.

## Accessibility
- Tap targets minimum 120px. High contrast. No small text.
- Auto-plays greeting on load (user gesture required on some browsers — tap to start).
