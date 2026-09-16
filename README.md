# The Read

A dating-conversation copilot for one specific person, in one specific city.
It reads a match conversation, works out where it actually stands, picks a
track, and writes replies in his voice — not in a chatbot's.

Two front ends over one brain:

| | What it is | When to use it |
|---|---|---|
| **`/rizz` skill** | `.claude/skills/rizz/` — paste a screenshot into Claude, get the read and three drafts | Anywhere Claude runs. No setup, no API key |
| **The web app** | `app/index.html` — a phone-friendly page that calls Claude from inside itself | Mid-conversation, on your phone |

## How it works

Five steps, every time:

1. **Read** — pull the facts out of the screenshot: stage, who spoke last, the
   gap, live threads, what's known about logistics.
2. **Score** — the investment ratio. Count her signals (message length,
   questions asked, who initiates, whether she plays along) against his. This
   is the engine; everything else follows from it.
3. **Stage** — S0 matched through S5 post-date, each with one objective and one
   failure mode. S2 (banter) is where conversations die.
4. **Track** — FAST, BUILD or PARK, decided by reading *her* rather than by
   asking him what he wants. He doesn't know in advance; it depends on the
   girl. So the tool decides per conversation, and re-decides every time.
5. **Write** — three drafts from genuinely different angles, each labelled with
   what it does and what it risks, plus what the next two messages are for.

## What's in the skill

- `SKILL.md` — the operating procedure above, with the hard rules that get
  enforced on every draft
- `references/voice.md` — his register, reverse-engineered from a real sent
  message, plus a sample bank to grow. **Add real messages here over time** —
  ten real samples beat any amount of inference from one
- `references/playbook.md` — patterns per situation: openers, the low-effort
  reply, the ask, the two-option close, flakes, the single revive, post-date
- `references/dates.md` — Sydney venues by area and tier, with the rules that
  make a first date convert (drinks not dinner, near her, second venue in your
  pocket)
- `references/dynamics.md` — what the research actually supports about mate
  value and modern dating, and which parts of the surrounding folklore don't
  survive contact with the data

## Using it

**Skill** — in Claude Code or the Claude app, with this repo open:

```
/rizz
```

Then paste the screenshot. Or just paste a screenshot and ask what to send —
the skill triggers on its own.

**App** — open `app/index.html` as a published Artifact, drop in a screenshot,
hit *Read it*. It needs Claude to be reachable from the page; opened as a bare
local file it'll tell you to use the skill instead.

## Honest limits

The tool optimises texting, which is roughly the seventh most important lever
in online dating — behind photos, volume, speed to date, and the controllable
parts of attractiveness. If matches are scarce, this won't fix it, and
`references/dynamics.md` says so in more detail. If matches are fine and
conversations die, this is the right instrument.
