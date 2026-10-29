# Omenra docs

Documentation for **Omenra** — a lab where intelligence is born: agents, models, tools, bots and robots built to anticipate. Published at `docs.omenra.si`.

## Structure

```
docs.json                  site config: name, colours, logo, navigation
index.mdx                  what Omenra is, and the name
vision.mdx                 the thesis: prediction, not description
quickstart.mdx             the seven decisions to a first agent
glossary.mdx               the six words that carry the platform

births/                    the five kinds of artefact
  agents, models, tools, bots, robots

intelligence/              how it thinks
  prediction, memory, autonomy, orchestration

build/                     lifecycle, evaluation
control/                   safety, governance
company/                   about (name story, design partners), roadmap
faq.mdx
```

## Brand

Colours, sampled from the icon: `#3b5bff` disc, `#0b1020` space, `#f5f6f8` suit, `#cf9a63` tether. Wordmark in `logo/light.svg` and `logo/dark.svg`; standalone app icon in `icon.svg`; favicon in `favicon.svg`.

The astronaut orbits the disc continuously — CSS animation inside each SVG, so it runs wherever the file is used as an `<img>`, with no JavaScript. Timing: one orbit every 26s (`orbit`), counter-rotated by `level` so it stays upright, a ±9° `tilt` so it drifts rather than slides, a 90s `drift` on the starfield for parallax, and two `twinkle` stars. `prefers-reduced-motion: reduce` stops all of it and leaves a clean static frame.

## Publishing

<Steps>

1. **Preview**

   ```bash
   npx mint dev
   ```

2. **Get the files into the Mintlify project**

   Push this directory to the repo connected to the Mintlify project (or paste pages through the dashboard). The old Mintlify starter kit's `essentials/`, `development.mdx` and `api-reference/` should be deleted — nothing in `docs.json` references them.

3. **Point the domain**

   Mintlify → **Settings → Custom domain** → add `docs.omenra.si`. Then create the DNS record it shows you at the registrar for `omenra.si`: a `CNAME` for host `docs`, plus any verification TXT it asks for. Note that `omenra.si` itself does not resolve yet, so the apex needs to be set up first.

</Steps>

## What is a standard, not a shipped feature

This site defines the platform being built. It contains **no command-line, no SDK and no API endpoints**, because none exist yet — deliberately, so the docs cannot promise something that does not run. Pages that describe behaviour (`Autonomy`, `Safety`, `Lifecycle`) describe the model we are building to.

Two places to keep honest as the product lands:

| Page | Needs a rewrite when |
| --- | --- |
| `build/lifecycle.mdx` | The real contract manifest schema exists — replace the illustrative YAML |
| `quickstart.mdx` | There is an actual first-run path to document |
| `company/roadmap.mdx` | Anything in "Now" ships or slips |
| `faq.mdx` | The "is there a product" and "is it open source" answers change |

## Things to confirm with the founder

- **Name.** The docs are built on **Omenra** to match `omenra.si` and `docs.omenra.si`. If the name changes, it is `docs.json` → `name`, plus the two logo SVGs, plus the "The name" section in `company/about.mdx`.
- **Contact.** `hello@omenra.si` is used in `company/about.mdx` and `faq.mdx`. Confirm the mailbox exists before publishing.
- **Refusals.** The "what we will not build" list in `control/safety.mdx` (lethal action, credit/employment/insurance/liberty scoring, election influence, self-granted permissions) is my draft of a defensible policy. It is your company — edit it to match what you actually commit to, but keep it specific. A refusal list that refuses nothing reads as marketing.
- **Positioning.** "Born to rule the world" is framed in `vision.mdx` as *foresight without jurisdiction*, with an explicit paragraph on why we would not build systems that rule. Stronger or softer is your call; the safety pages depend on this framing.

## Archive

`archive/ioc-docs/` holds an earlier, unrelated docs site (IoC/threat-intelligence platform) built by mistake from a similarly named product at `omenra.lutpod.com`. It is kept only so nothing is lost; it is not part of this site and can be deleted safely.
