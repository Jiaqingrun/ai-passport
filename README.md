<p align="right">
  <a href="README.zh_CN.md">简体中文</a> · <strong>English</strong>
</p>

# AI Passport projects

Two applications for the FoloToy AI Passport — an ESP32-C3 board with 8 MB of
flash, no PSRAM, a 240 × 320 panel and three keys. Each application lives in its
own repository or branch; this page is the catalog for the fork and points at the
one that is current.

## Dust of Worlds — God Simulator

A world that keeps evolving while the player mostly watches. Six peoples — Human,
Beast, Avian, Scale, Insect and Wood — spread over a generated archipelago, found
cities, split, ally, fight and die out on their own; where two peoples meet, a
hybrid people (Human-Beast, Bird-Scale, Beast-Bird, Wood-Insect) can be born with
traits from both parents. The player never commands anyone: divine power is spent
on disasters, blessings and answers to prayers, and the chronicle says what came
of it.

- **Five pages, three keys**: World, Chronicle, Data, Species and Atlas. Up and
  Down step and accelerate, OK executes and pauses, holding Up or Down flips
  pages, holding OK sleeps the screen while the world keeps running at 1×.
- **Three rulers with their own stories**: KANE issues absurd edicts that drag a
  civilization downward, Daji works passively from the Beast tribes, and the First
  Emperor unites the Human tribes and slows time while he reigns.
- **Prayers, holy sites and wonders**: tribes ask for help and the world pauses
  for an answer; high civilizations raise star gates, sky towers and great temples.
- **Twilight and rebirth**: when an empire-tier people exists alongside four
  surviving peoples, the dusk countdown starts; the old world ends, its wonders
  become ruins, and the next cycle begins with a new continent.

Repository: [Jiaqingrun/ai-passport-dust-of-worlds](https://github.com/Jiaqingrun/ai-passport-dust-of-worlds),
branch `main` (v0.51). Also published in the community library as project
`community-c04b753d`, and archived upstream in
[`docs/reference/jiaqingrun/dust-of-worlds/`](https://github.com/FoloToy/ai-passport/tree/main/docs/reference/jiaqingrun/dust-of-worlds).

## Ember (Ashbox)

An offline post-apocalyptic base builder on the same board: a hearth home,
expeditions out of it, base building, trade, injury and medicine, wanderers, and a
USB save manager. Not a hardware-test demo and not an online game — the whole
thing works with the radio off.

Branch: `feature/ashbox-ember` in this fork
(<https://github.com/Jiaqingrun/ai-passport/tree/feature/ashbox-ember>), with the
project conventions in `PROJECT.md` and the product docs under `docs/ashbox/`.

## Building either application

Both target ESP-IDF 5.5.3 and the stock AI Passport partition layout:

```bash
source ~/esp/esp-idf-v5.5.3/export.sh
idf.py build        # application image
idf.py merge-bin    # merged image for a full flash at 0x0
```

Flashing the application alone keeps the stored world or save data; a merged image
over the whole flash does not promise to preserve it. The two repositories carry
their own build and flash notes — read those rather than reusing a command from
this page.

## Reference

The reusable learnings behind these applications are archived upstream under
`docs/reference/jiaqingrun/`: the simulation and save format, the rendering and
audio path, the full-screen map page, and the optional-row grid. They are written
as reference material, not as rules.
