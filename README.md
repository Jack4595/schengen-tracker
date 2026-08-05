# Schengen Tracker

A calculator for the Schengen 90/180 rule. Enter your trips and it tells you how
many days you have left, when you have to leave, and when you next get a clean
90 days back.

Single `index.html` — no build step, no dependencies, no server. Trips are kept
in the browser's local storage, on the device, unless you turn on sync.

## The rule

You may spend 90 days in the Schengen area in any rolling 180-day window. The
window moves with you: every day, the day 180 days ago drops out and frees up
whatever you spent on it. That is what makes it awkward to do in your head, and
what this page does for you.

## What it shows

Three numbers, for the trips you have entered:

- **Max stay** — how many more consecutive days you can stay from today
- **Latest exit** — the last date you can leave without overstaying
- **Next full 90** — the first date a fresh 90-day allowance is available

"Next full 90" is split in two, because the honest answer is two dates:

- **Safe** — the window is completely empty; you have all 90 days with no history
  behind you
- **Legal** — the earliest date you could begin an unbroken 90-day stay, using
  days as they free up beneath you

## Use it

Open `index.html` in a browser. On iOS, add it to the home screen and it runs
full-screen like an app.

Trips can be pasted in as CSV — `entry, exit, country`, dates as `DD/MM/YYYY`.

## Sync across devices (optional, off by default)

Sync uses [jsonbin.io](https://jsonbin.io) as the store. Create a free account,
copy your access key, and paste it into **Sync setup** on each device. The first
device creates a sync ID; paste that ID on the others to point them at the same
trips.

With sync off, nothing is sent anywhere. With it on, your trip data is held in
your jsonbin account — so it is as private as that account is.

## Caveats

This is a planning aid, not legal advice. It counts days by the standard rule —
day of entry and day of exit both count as days in the area. It does not know
about national long-stay visas, residence permits, or the bilateral visa-waiver
agreements some countries still honour, any of which change the maths. Check
anything important against an official source before you book.
