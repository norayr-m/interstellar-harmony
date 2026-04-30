# Interstellar Harmony — Orbital Transformer

> This is an amateur engineering project. We are not HPC professionals and make no competitive claims. Errors likely.

A browser demo where a small reasoning system runs as three concentric phases on a ranked grid: tokens appear at the outer rank, spiral inward through processing, and spiral back out as the decoded output. Cosmetically inspired by Hans Zimmer's score for Christopher Nolan's *Interstellar* (2014) — the organ in the dust, time as a physical dimension, information moving through layers we do not directly inhabit.

**[Live demo →](https://norayr-m.github.io/interstellar-harmony/)**

## What it does

Three phases play out, in order, on a ranked board (think onion-shell layout from rank 6 outermost to rank 0 at centre):

1. **Encode.** Input tokens appear on rank 6 (the outer shell). They are the "raw" signal entering the system.
2. **Processing.** Each token spirals inward, rank by rank. At every step it interacts with the local pattern store and the local rules. This is the "thinking" phase.
3. **Decode.** Once the spiral hits the centre and stabilises, tokens spiral back outward through the ranks and emerge as decoded output.

The whole loop runs visibly. You can press SOLVE and watch encode → process → decode play as a single continuous animation. The reasoning engine in the middle is a small knowledge-graph + pattern-solver pair, not a real LLM.

## Why it matters (DRT angle)

This is the **forward/backward pass slice**. The framework asks: if you have a function on a ranked, distributed substrate, what does it look like for information to enter, be transformed, and come back out — and what part of the output is in the input vs. added by the transformation?

Three structural points are visible in the demo:

1. **Rank as time.** The rank coordinate carries the role time usually plays in a transformer or RNN. A token "going inward" is the same shape as a token "going forward in time" through layers.
2. **Encoder/decoder symmetry.** The forward spiral inward and the backward spiral outward use the same substrate; the path is just reversed.
3. **Aggregate at the centre.** Whatever the central rank computes plays the role of the aggregate in the framework.

The honest current claim from the v0.1 draft is conditional and modest: under four hypotheses and a bounded computational budget, the aggregate exposes structural features not accessible from the original signal alone within the same budget. The earlier "norm-growth" prose has been retracted. This demo is a visual playground for the encode/process/decode shape, not a proof of the underlying claim.

## How to run

Single HTML, open in a browser:

```
git clone https://github.com/norayr-m/interstellar-harmony.git
open interstellar-harmony/index.html
```

Press SOLVE. No build step, no server, no external dependencies beyond a modern browser.

## Companion work

- **DRT_Pipeline** — the same forward/backward shape applied to BWV 847 instead of token streams.
- **DRT_Orbital_Solver** — orbital-mechanics framing of the same encode/solve/decode skeleton.

## References

- Distributed Reconstruction work — v0.1 in preparation, N. Matevosyan and A. Petrosyan.
- Zimmer, H. — *Interstellar* original soundtrack (2014), only as aesthetic source.

Visualization co-authored with Claude (Anthropic).

## Author

Norayr Matevosyan

## License

GPLv3
