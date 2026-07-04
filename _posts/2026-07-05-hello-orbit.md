---
title: "Hello, Orbit — how transmissions work"
description: "TX-001: the station's blog is online. Code blocks, callouts, images, and GIFs — everything a transmission can carry, demonstrated live."
---

Welcome aboard. This is the first transmission from the station — and it doubles as the field manual for writing the next ones. Everything a post can carry is demonstrated below, so future-me (or curious visitors reading the [source](https://github.com/ameycodes/ameycodes.github.io)) can see exactly how it's done.

Publishing a new transmission takes three steps: write a Markdown file, name it `_posts/YYYY-MM-DD-slug.md`, push to `main`. GitHub Pages builds it into a page automatically. No build tools, no deploy scripts. The station handles its own paperwork.

## Code blocks

Fenced code blocks get syntax highlighting matched to the station's instrument palette:

```python
def stable_orbit(velocity: float, altitude_km: float = 412) -> bool:
    """Anything above 7.66 km/s at this altitude stays up. Roughly."""
    ORBITAL_VELOCITY = 7.66
    return velocity >= ORBITAL_VELOCITY and altitude_km > 100
```

```javascript
// the docking simulator's core loop, simplified
function step(dt) {
  ship.vx += thrust.x * dt;
  ship.vy += thrust.y * dt;   // no friction in space — brake early
  ship.x  += ship.vx * dt;
  ship.y  += ship.vy * dt;
}
```

Inline code like `kubectl get pods` works too.

## Callouts

Four callout classes are available — write a `<div>` with `markdown="1"` so Markdown keeps working inside:

<div class="callout note" markdown="1">
**Note** callouts are for context — the thing a reader should know before continuing.
</div>

<div class="callout tip" markdown="1">
**Tip** callouts are for shortcuts. For example: type `dock` in the [station terminal](/#terminal) and thank me later.
</div>

<div class="callout warn" markdown="1">
**Warning** callouts are for sharp edges. Friday deploys, `rm -rf`, unbounded retry loops.
</div>

<div class="callout danger" markdown="1">
**Danger** callouts are for the stories that end with "and that's how we learned about backups."
</div>

## Images and GIFs

Drop files in `assets/tx/` and reference them with standard Markdown. GIFs animate like any image, and a `<figure>` adds a proper caption:

<figure>
  <img src="/assets/tx/orbit-diagram.svg" alt="Diagram of three orbit rings around a core, labeled fundamentals, backend, and DevOps">
  <figcaption>FIG 01 — The station's skill array. You've seen this somewhere before.</figcaption>
</figure>

For animation-heavy demos, a `<video autoplay loop muted playsinline>` tag keeps file sizes sane compared to giant GIFs.

Third-party embeds work too, since this is just HTML underneath. For example — actual security-camera footage of the flight engineer realizing the "harmless config change" he deployed on Friday at 17:58 has reached production:

<figure style="max-width:420px">
  <div class="tenor-gif-embed" data-postid="5255913" data-share-method="host" data-aspect-ratio="0.932836" data-width="100%"><a href="https://tenor.com/view/pug-shocked-surprised-what-turn-gif-5255913">Pug Shocked GIF</a>from <a href="https://tenor.com/search/pug-gifs">Pug GIFs</a></div>
  <figcaption>FIG 02 — CREW REACTION, COLORIZED. THE PAGER RANG 90 SECONDS LATER.</figcaption>
</figure>
<script type="text/javascript" async src="https://tenor.com/embed.js"></script>

## Everything else

Blockquotes, lists, and tables all wear the station livery:

> Any sufficiently advanced deployment pipeline is indistinguishable from a very patient colleague.

| Subsystem | Status | Notes |
|-----------|--------|-------|
| Blog | ONLINE | You are reading it |
| Coffee | CRITICAL | In the good sense |

---

That's the whole manual. Transmission ends. More to follow — probably about Spring Boot, Kubernetes, or whatever breaks next week in an interesting way.
