# Always-On Personal Agents as Competing Operating Primitives

**A Comparative Study of OpenAI Dots and Grok Bot**

beamnxw · working paper, not peer reviewed · 29 September 2026

This is the readable GitHub copy of the paper. The typeset version with TikZ figures is [`dots-vs-grok-bot.pdf`](./dots-vs-grok-bot.pdf) / [`dots_vs_grok_arxiv.tex`](./dots_vs_grok_arxiv.tex).

## Abstract

Persistent agents with dedicated cloud computers became a product category in August–September 2026. This working paper compares two instantiations of that category on the day OpenAI shipped Dots at DevDay 2026: OpenAI Dots, a single named chief-of-staff embedded in ChatGPT and powered by GPT-6 Astra; and Grok Bot (SpaceXAI / xAI, distributed through Cursor), a roster of named teammates that share one user-scoped cloud computer. We argue that the products implement the same primitive—an always-on agent, a durable machine, a connector graph, and an approval gate—but disagree on the unit of work. Dots attaches a virtual machine to an agent and postpones multi-agent coordination. Grok Bot attaches a virtual machine to a user and already routes work across named roles, including Team Bots launched on 28 September 2026. The paper tabulates architecture, memory, channels, pricing, safety controls, and recommended operating conditions, and proposes a fourteen-day bake-off protocol. It is a research snapshot, not a benchmark and not an endorsement.

**Keywords:** persistent agents, cloud computers, ChatGPT Dots, Grok Bot, multi-agent systems, approval gates, Team Bots, specialist Dots

## 1. Introduction

By late September 2026 the industry had converged on a form factor that is no longer a chatbot. Meta Muse (8 September), Instinct, OpenClaw, Poke, Gemini Spark and related systems all give a model a durable workspace and permission to continue after the session ends.

OpenAI Dots launched on 29 September 2026 inside ChatGPT. Grok Bot launched in early beta on 11 August 2026, widened to paid Cursor and SuperGrok plans on 26 August, and added Team Bots on 28 September.

The public copy is almost interchangeable: always-on, own computer, works while the laptop is closed, asks before irreversible acts. The implementations are not interchangeable. This paper treats them as competing operating primitives rather than as feature checklists.

Shared primitive:

```
frontier model  →  cloud VM (browser + fs + tty)  →  connector / plugin graph  →  approval gate
```

P = (M, V, C, G). Products differ on how V is bound and how many agents share C and G.

Timeline:

- 11 Aug 2026 — Grok Bot beta
- 26 Aug 2026 — Grok Bot widened to paid Cursor / SuperGrok plans
- 8 Sep 2026 — Meta Muse
- 28 Sep 2026 — Team Bots
- 29 Sep 2026 — Dots + ChatGPT Space

## 2. Method and scope

Sources: vendor documentation, Help Center / Learn pages, launch posts, and same-day third-party reporting. No head-to-head task suite exists for Dots on launch day. Vision claims (teams of Dots, SMS waitlists, Agent 365 pilots) are labelled as such. Prices and geo gates move.

## 3. Product definitions

**OpenAI Dots.** An always-on agent in the ChatGPT sidebar. Powered by GPT-6 Astra. Own cloud computer and browser. 4,000+ ChatGPT plugins. Channels: ChatGPT, Slack, Teams, voice; SMS waitlisted. One primary Dot per eligible account. Teams of Dots envisioned. Specialist Dots previewed for orgs, including a Microsoft Agent 365 path.

**Grok Bot.** A roster of persistent named teammates. One persistent cloud computer per *account* (browser, filesystem, terminal) shared by all of that user’s Bots. Connectors where they exist; computer-use where they do not. Role memory, DMs, group chats, demonstration learning (skill → routine), schedules and webhooks. Team Bots share team context with private per-user threads. Standalone app: macOS, Windows, Linux, iOS, Android. Not a mode of Grok chat and not a mode of ChatGPT.

## 4. The architectural fork

Dots attaches a machine to an **agent**. Inspect / take over / return control. Local laptop is opt-in, off by default, one machine. A login on the laptop does not sign the Dot in.

Grok Bot attaches a machine to a **user**. All Bots share files, cookies and sessions. Isolation is per user, not per Bot. Docs warn: do not treat separate Bots as a security boundary. One computer-use task per Bot screen at a time. Handoff is cheap.

Failure modes invert. Client-separated cookies → per-agent VM (Dots / specialist Dots). Human must not be the router → Grok Bot roster.

## 5. Master comparison

| Dimension | OpenAI Dots | Grok Bot |
|---|---|---|
| Vendor | OpenAI | SpaceXAI / xAI via Cursor |
| Launch | 29 Sep 2026 | 11 Aug 2026; Team Bots 28 Sep |
| Metaphor | One chief of staff in ChatGPT | Roster of named coworkers |
| Agents on day one | One primary Dot | Many named Bots |
| Multi-agent now | Vision only | DM, group chats, handoffs, parallel |
| Org agent | Specialist Dots preview; Agent 365 | Team Bots GA |
| Home surface | ChatGPT + Slack + Teams | Standalone Grok Bot app |
| Model | GPT-6 Astra | Grok 4.6 / 4.7 mix |
| Cloud computer | One VM per Dot | One VM per user, shared |
| Agent isolation | Stronger between agents | Weak between Bots |
| Integrations | 4,000+ plugins | Connectors + computer-use + native X |
| Background | Proactive research, read-only | Skills, routines, webhooks |
| Entry price | ChatGPT Pro / Business Premium | Cursor Pro $20 or SuperGrok $30 |
| Chat metering | Dot chat does not eat ChatGPT caps | Bot usage separate from chat/editor |
| Heavy work | Codex / Work tasks count | Weekly Bot grant; optional on-demand |
| Geo gate | Pro blocked EEA / CH / UK at launch | No matching published block |
| Maturity this date | Hours old | Six weeks in paid production |

## 6. Memory and coordination

Dots: ChatGPT memory + Dot notes + active thread + background agents under one agent.

Grok Bot: per-Bot role memory reunited on the shared VM; skills / routines; Team Bot context orthogonal to per-user threads.

## 7. Distribution, workspace and coding

Dots wins distribution (ChatGPT surface, Slack, Teams, Space). Coding is delegated into Codex / ChatGPT Work and hits those meters.

Grok Bot wins the dedicated workstation (roster, Agent Computer). Coding lives next door in Cursor / Grok Build. Bot usage is a separate weekly bucket. Native X connector. Computer-use on no-API tools is more central.

## 8. Pricing and access

Neither product has a standalone SKU.

Dots: on the ChatGPT pricing matrix under Pro, not Plus. First Dot included. Dot conversation does not count against ChatGPT caps; Codex/Work does. Enterprise / Edu / Healthcare beta is admin-gated. Pro geo-blocked in EEA, Switzerland, UK at launch.

Grok Bot: Cursor Pro $20, SuperGrok $30, up to Cursor Ultra $200 and SuperGrok Heavy $300. Weekly Bot allowance. Optional on-demand after the grant.

## 9. Safety

Shared pipeline:

```
intent → Custom Rules / Bot policy → auto-review → act or ask / takeover
                                              ↔ always-human (password, pay, 2FA, delete)
```

Dots: four Custom Rule behaviors; Auto-review cannot be disabled by the Dot; proactive layer is read-only; local computer starts off.

Grok Bot: takeover for passwords / 2FA / CAPTCHA / payments; Auto Review on outbound; Enterprise IAM; shared-computer warning is the distinctive disclosure.

Category risk is the keys you hand over, not the mascot.

## 10. What is not yet real

- Teams of Dots (blog sentence)
- Specialist Dots / Agent 365 as self-serve
- Dots SMS / iMessage (waitlist)
- Published Grok Bot weekly task counts
- Independent head-to-head bench including Dots on 29 Sep 2026

## 11. Fourteen-day bake-off

Same brief → Job A monitor (read-only) / Job B assemble (multi-app) / Job C parallel handoff → score artifacts + VM takeover count.

Week one observation only. Week two may add local-computer access if Job B requires it.

## 12. Conclusion

The category is settled. The operating theory is not. OpenAI bets on one Astra-class agent inside a surface with more than a billion weekly users. xAI bets that work already has named owners who should share a machine.

On 29 September 2026, Grok Bot is the more complete multi-agent operating system. Dots is the stronger single-agent, single-surface, single-model wager. Choose the primitive that matches the failure mode you actually have, then run the bake-off before moving secrets onto either machine.

## License

CC BY 4.0. Not affiliated with OpenAI or xAI.
