# BreachLab Writeups

Writeups from my run through [BreachLab](https://breachlab.org/), organized by track and level as I clear them.

## What is BreachLab

BreachLab is an offensive security training platform, now expanding into defensive work too: Sentinel, its first blue-team track (SOC, detection, DFIR), went live alongside the offensive ones. Every level runs on real infrastructure: SSH boxes, containers, misconfigurations you actually exploit instead of read about. The curriculum spans 13 tracks in total, from Linux fundamentals to binary exploitation; five are live today (Ghost, Phantom, Specter, Mirage, Sentinel), the other eight are planned and not yet playable.

Site: [breachlab.org](https://breachlab.org/)

## About this repo

This documents my own path through the tracks: the reasoning behind each step, the commands I ran, the dead ends I hit first. It is not a solutions guide. BreachLab's rules ask writeups to teach technique, not hand over the answer, so flags and passwords stay out of these pages. Text uses `[REDACTED]` in their place, and screenshots get the same treatment before they go in.

## Structure

```
Breachlab-Writeups/
├── README.md               this file
├── _template/               level writeup template, read before starting a new one
└── <Track>-Track/
    ├── README.md            track intro, access details, progression table
    ├── screenshots/         images for every level in the track
    └── Level N - Title/
        └── README.md        writeup for that level
```

Empty level folders carry a `.gitkeep` placeholder until that level gets solved and written up.

## Tracks

Only Ghost is covered here so far. I'll add a folder for each live track as I get to it; planned tracks (Nexus, Oracle, Wraith, Shadow, Cipher, Prism, Venom, Flux) aren't up yet.

| Track | Focus | Levels | Progress |
|---|---|:---:|:---:|
| [Ghost](./Ghost-Track/README.md) | Linux & shell fundamentals | 22 | 3 / 22 |
