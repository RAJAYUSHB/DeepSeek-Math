# Hold — a hands-free workout timer

A voice-controlled interval timer for people who are mid-exercise and can't touch or look at a watch.
It's a single file (`index.html`) with no build step, no dependencies and no backend.

## Run it

```bash
cd voice-stopwatch && python3 -m http.server 8000
```

Open http://localhost:8000 in Chrome, Edge or Safari. The microphone needs `localhost` or HTTPS, so to use it
on a phone, host it anywhere with HTTPS (GitHub Pages, Netlify…) and use *Add to Home Screen*.

## How it works

1. **Pick a workout:** Plank, Push-ups, Squats, Jumping Jacks, Lunges, Wall Sit, HIIT, Stretch or Free Timer.
2. **Pick a duration:** 30 s, 45 s, 1 min… or a custom one. Sets and rest between sets are optional.
3. **Tap Ready**, allow the mic, get into position and say **"start"**.

| Say | Does |
| --- | --- |
| "start", "go", "begin", "let's go" | Start (or resume) |
| "stop", "pause" | Pause |
| "resume", "continue", "keep going" | Resume |
| "reset", "restart", "start over" | Back to the start |
| "skip", "next" | Skip the rest period |
| "finish" | End now and log it |
| "again", "repeat" | Run it again once done |

**Feedback you don't have to look at:** a 3-2-1 lead-in, beeps on the last 3 seconds, spoken
"Go / Halfway / Ten seconds / Rest / Done" (can be turned off), vibration on Android, and the screen stays awake.

**Progress you can feel:** the screen fills from the bottom like a glass filling up. Marks at 25%, ½ and 75%
turn into badges as you pass them, set pills fill in one by one, and finishing shows a check, today's total
and a 7-day chart (stored on the device only).

## Prompt used

> Build a **hands-free interval timer for people who are exercising**. It runs on a phone browser, and voice
> commands start and stop it because the user's hands are busy and they can't look at a watch.
>
> **Flow:** 1) Pick a workout from a grid of icons (Plank, Push-ups, Squats, Jumping Jacks, Lunges, Wall Sit,
> HIIT, Stretch, Free timer). 2) Pick a duration. Each workout suggests presets (30 s, 45 s, 1 min…) and there's
> a Custom stepper. Sets (1–10) and rest between sets are optional. 3) Timer screen.
>
> **Voice:** continuous listening. "start / go / begin", "stop / pause", "resume / continue",
> "reset / restart", "skip / next" (skips rest), "finish", "again". Each recognized command flashes on screen.
> Big tap buttons are the fallback.
>
> **Eyes-free feedback:** a 3-2-1 lead-in so you can get into position, beeps for the last 3 seconds, a spoken
> "Halfway", "Ten seconds", "Rest" and "Done", vibration where the phone supports it, and the screen stays awake.
>
> **Visual:** no round stopwatch. The screen fills from the bottom like a glass filling up, in the workout's
> soft colour. Marks at 25%, 50% and 75% turn into ticks as you pass them, and set pills fill one by one.
> Finishing shows a check animation, today's total and a 7-day bar chart, all stored on the device.
>
> **Style:** minimal, soft pastels, SF Pro/Helvetica, thin line icons, light and dark mode, sized for a phone.
> No build step and no backend.

## Limits

- Voice recognition uses the browser's Web Speech API: Chrome/Edge (desktop and Android) and Safari (iOS 14.5+).
  Firefox doesn't support it, so use the buttons there.
- Chrome sends audio to Google's speech service to recognize it. Commands are in English.
- Very loud music can drown out commands. Short, clear words like "stop" work best.
