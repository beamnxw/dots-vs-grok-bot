# Always-On Personal Agents as Competing Operating Primitives

**A comparative study of OpenAI Dots and Grok Bot**

[![PDF](https://img.shields.io/badge/paper-PDF-b31b1b)](./paper/dots-vs-grok-bot.pdf)
[![TeX](https://img.shields.io/badge/source-LaTeX-008080)](./paper/dots_vs_grok_arxiv.tex)
[![Read online](https://img.shields.io/badge/read-Markdown-2088FF)](./paper/PAPER.md)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![Snapshot](https://img.shields.io/badge/snapshot-29%20Sep%202026-111111)](#)

Working paper · not peer reviewed · snapshot date **29 September 2026** (the day OpenAI shipped Dots at DevDay).

## Links to send

| What | URL |
|---|---|
| Repo | https://github.com/beamnxw/dots-vs-grok-bot |
| PDF in browser | https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/dots-vs-grok-bot.pdf |
| Raw PDF | https://github.com/beamnxw/dots-vs-grok-bot/raw/main/paper/dots-vs-grok-bot.pdf |
| Readable Markdown | https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/PAPER.md |
| LaTeX source | https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/dots_vs_grok_arxiv.tex |

## One-paragraph claim

Both products instantiate the same primitive — a frontier model, a durable cloud machine, a connector graph, and an approval gate. They disagree on the unit of work. **Dots** attaches a virtual machine to *one named agent* inside ChatGPT (GPT-6 Astra). **Grok Bot** attaches a virtual machine to *the user account* and already routes work across a roster of named teammates, including Team Bots (28 Sep 2026). Dots is the stronger single-agent / single-surface wager. Grok Bot is the more complete multi-agent operating system on this date.

## Figures (in the PDF / TeX)

1. Shared primitive P = (M, V, C, G)
2. August–September 2026 timeline
3. VM binding: machine-per-agent vs machine-per-user
4. Unit of work (one Dot vs Scout / Writer / Sender)
5. Memory topology
6. Channel surfaces
7. Approval pipeline
8. Fourteen-day bake-off protocol

## Build the PDF

```bash
cd paper
pdflatex dots_vs_grok_arxiv.tex
pdflatex dots_vs_grok_arxiv.tex
cp dots_vs_grok_arxiv.pdf dots-vs-grok-bot.pdf
```

Needs TeX Live with `article`, `tikz`, `pgfplots`, `lmodern`, `hyperref`, `booktabs`, `tabularx`.

```bash
make
```

## Cite

```bibtex
@misc{beamnxw2026dots,
  title        = {Always-On Personal Agents as Competing Operating Primitives:
                  A Comparative Study of OpenAI Dots and Grok Bot},
  author       = {beamnxw},
  year         = {2026},
  month        = sep,
  note         = {Working paper. Snapshot date 29 September 2026},
  howpublished = {\url{https://github.com/beamnxw/dots-vs-grok-bot}}
}
```

See also [`CITATION.cff`](CITATION.cff).

## Scope

Vendor docs, Help Center / Learn pages, launch posts, and same-day reporting. Not a head-to-head task benchmark. Prices, geo gates, and model identity will move.

## License

[CC BY 4.0](LICENSE). Product names are trademarks of their owners. Not affiliated with OpenAI or xAI.
