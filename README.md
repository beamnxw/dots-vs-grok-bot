# Always-On Personal Agents as Competing Operating Primitives

**A comparative study of OpenAI Dots and Grok Bot**

[![Read the paper](https://img.shields.io/badge/read-the%20paper-2088FF)](https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/PAPER.md)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![Snapshot](https://img.shields.io/badge/snapshot-29%20Sep%202026-111111)](#)

Working paper · not peer reviewed · snapshot date **29 September 2026** (the day OpenAI shipped Dots at DevDay).

## Send this link

**https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/PAPER.md**

That file is the paper. GitHub renders it. No download required.

Repo home: https://github.com/beamnxw/dots-vs-grok-bot

## One-paragraph claim

Both products instantiate the same primitive — a frontier model, a durable cloud machine, a connector graph, and an approval gate. They disagree on the unit of work. **Dots** attaches a virtual machine to *one named agent* inside ChatGPT (GPT-6 Astra). **Grok Bot** attaches a virtual machine to *the user account* and already routes work across a roster of named teammates, including Team Bots (28 Sep 2026). Dots is the stronger single-agent / single-surface wager. Grok Bot is the more complete multi-agent operating system on this date.

## What is in the repo

```
README.md
LICENSE                 CC BY 4.0
CITATION.cff
Makefile
paper/PAPER.md          the paper (open this)
paper/README.md
```

The typeset PDF with TikZ figures is not stored in git (GitHub's file API here cannot take a binary blob). To attach it:

1. Open https://github.com/beamnxw/dots-vs-grok-bot/upload/main/paper
2. Drop `dots-vs-grok-bot.pdf` and optionally `dots_vs_grok_arxiv.tex`
3. Commit

After that, these two URLs will start working:

- https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/dots-vs-grok-bot.pdf
- https://github.com/beamnxw/dots-vs-grok-bot/blob/main/paper/dots_vs_grok_arxiv.tex

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

## License

[CC BY 4.0](LICENSE). Not affiliated with OpenAI or xAI.
