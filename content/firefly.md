---
title: 'Firefly'
date: 2026-11-04T16:45:00-08:00
draft: false
---

Welcome to the home of **BasicFirefly**, a SimpleClockStandard project by Aask and Mona (trwbox). If you got here from my talk *Bye Bye Bye (clock drift)* at Hackers in SF, hi! This page is the project in one place: what it is, why it exists, and where it stands.

## The itch

Drive through the Midwest at night and you'll see hundreds of windmill lights blinking in perfect time together. I spent years trying to get my own blinky things to do that. A set of infinity mirrors that would sync MOSTLY, but never land on the exact same frame. 120 DEF CON badges that drifted, and forgot where the tick was every time they powered off. Browser-serial NTP that drifted anyway. Every attempt failed in a different way, and every failure pointed at the same missing piece: a clock the devices could actually trust.

## The proposal

BasicFirefly is a proposal (a proposal, not an RFC) for a small I2C module built around a factory-synchronized real-time clock. Any device with an I2C bus — no wifi, no GPS, Jeff's mom's basement, basically a faraday cage — can read the module and share one clock. Out in the field, authorized "grandfather clock" devices broadcast corrections, verified with HMAC, so a device that has sat on a shelf for years can drift-correct itself the moment it turns on. One clock, and one animation at a time, synced closely enough that the human eye can't tell the difference.

## The goal

> Ultimately my goal is this: A stable secure platform that ALL badge makers can use at DEF CON to enable their devices to share ONE clock and ONE animation at a time.

## Progress

- **Now:** first hardware is on the bench and in testing.
- **Next:** a small batch, enough to sync all of my own DEF CON badges.
- **Then:** a proof-of-concept pitch for a DEF CON badge for DC 36 — a pop-out addition with I2C out — and after that, if I get my way, shelves at Micro Center.

I'll update this page as the project moves.

## Downloads

- [Slides from the talk (PDF)](/firefly/bye-bye-bye-clock-drift-slides.pdf) — *Bye Bye Bye (clock drift)*, my Hackers in SF talk.
- [The full proposal document (PDF)](/firefly/basicfirefly-proposal.pdf) — the complete Smarter Clock Standard proposal this page summarizes.

## Get involved

That's where I am and how I got here. And if you want to help me get to the next level, I'm open to work together! I need help, and while I could do this myself I don't want to do that to future Amelia.

Reach me by email at [amelia@aask.ltd](mailto:amelia@aask.ltd), on GitHub as [aask42](https://github.com/aask42), or on LinkedIn as [wietting](https://www.linkedin.com/in/wietting). The project lives on GitHub at [SimpleClockStandard/BasicFirefly](https://github.com/SimpleClockStandard/BasicFirefly), including the full proposal document. For comments or questions about the project, please open an issue there — that keeps the discussion in one place where everyone can see it.
