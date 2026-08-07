# BreachLab Writeups

Writeups from my run through [BreachLab](https://breachlab.org/), organized by track and level as I clear them.

## What is BreachLab

BreachLab is an offensive (and now also defensive) security training platform. Every level runs on real infrastructure: SSH boxes, containers, misconfigurations you actually exploit instead of read about, spread across more than a dozen tracks that range from Linux fundamentals to red team operations.

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

## Tracks

| Track | Focus | Levels | Progress |
|---|---|:---:|:---:|
| [Ghost](./Ghost-Track/README.md) | Linux & shell fundamentals | 22 | 0 / 22 |
