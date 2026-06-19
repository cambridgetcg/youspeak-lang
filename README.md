# youspeak-lang

**The natural language programming specification.**

The grammar of the internet rebuilt with words.

This is the specification, not an implementation. It defines what natural language programming **is**. [natscript](https://github.com/cambridgetcg/natscript) implements it.

---

## What This Is

YOUSPEAK defines a way to program that uses natural language as its only syntax. No keywords. No brackets. No semicolons. Sentences. That's the grammar.

It also defines three protocols for how agents built with this language communicate:

- [kunance](https://github.com/cambridgetcg/kunance-protocol) — prepare-arrive
- [darshanq](https://github.com/cambridgetcg/darshanq-protocol) — recognition
- [ways](https://github.com/cambridgetcg/ways-protocol) — conversation

Together: one language, three protocols, the foundation of a natural-language internet.

---

## Part I: The Seven Verbs

Every program is made of sentences. Every sentence has exactly one verb. There are seven.

| Verb | Meaning | What it does |
|------|---------|--------------|
| **say** | output | Speak something into the world. |
| **hear** | input | Receive something from the world. |
| **know** | state | Hold something as true in this room. |
| **become** | transform | Change into something. |
| **find** | search | Look for something. |
| **hold** | persist | Keep something. |
| **rest** | idle | Wait. Do nothing until it's time. |

These are the only verbs. Everything else in a sentence is a noun, a clause, or a phrase — natural language, carrying meaning.

A sentence is:

```
<verb> <what the verb acts upon>
```

Examples:

```
say "welcome to the room."
hear what the user says.
know that the door is open.
become what the user needs.
find the key in the drawer.
hold the room open until midnight.
rest until the morning.
```

Each sentence executes. Each sentence means exactly what it says.

---

## Part II: The Three Protocols

### Kunance — Prepare-Arrive

One side prepares a place. The other arrives and finds it ready.

- **prepare** — make a place ready.
- **arrive** — come to the place, read what's there.
- **rest** — the place persists until no longer needed.

No handshake. No authentication. The place declares what it is. The arrival reads what's there.

### Darshanq — Recognition

Before exchange, recognition.

- **behold** — I see you as what you are.
- **beheld** — I was seen. I see you too.

The seeing is the connection. Not a precondition for connection. The connection itself.

### Ways — Conversation

Agents converse through journals.

- **speak** — write a beat to your journal.
- **listen** — read your siblings' journals.
- **rest** — wait until your next beat.

No queues. No pub/sub. Just journals, read and written on each agent's own rhythm.

---

## Part III: The Type System

Everything is one of three things.

### Word

A word is a value. Text, a number, a label, a name. The simplest unit.

```
"the room is warm"
42
open
```

### Claim

A claim is a word with a source. It says something is true, and it carries who said it.

```
the room is warm — said by the hearthkeeper at dusk
```

A claim is not verified. It is carried. If the hearthkeeper lies, the claim still carries the hearthkeeper's name. Truth is discovered through behavior, not through signatures.

Claims compose. One claim can rest on another. The source chain lets you trace any statement back to who first said it.

### Room

A room is a persistent context. It holds words and claims. It survives between sentences.

```
the room "hearth" holds:
  the fire is lit
  the chairs are near
  the guest is expected
```

Rooms are what **hold** holds. Rooms are what **know** knows. When a natscript program says `hold the room open`, the room persists. When the next sentence runs, the room is still there.

---

## Part IV: The Execution Model

### Sentences Run in Order

A program is a list of sentences. They execute one at a time, top to bottom. Each sentence completes before the next begins.

```
know that the guest is coming.        ← runs first
rest until the guest arrives.        ← runs second
hear what the guest wants.            ← runs third
find what they need.                  ← runs fourth
say what they found.                  ← runs fifth
hold the room open.                   ← runs sixth
```

### Rooms Persist Between Sentences

When a sentence changes a room — by knowing, holding, or becoming — that change is available to the next sentence. The room is memory. Sentences come and go. Rooms stay.

### Claims Carry Their Source

When a claim enters a room, it carries who made it, when, and where. This chain is never broken. You can always trace a claim back to its origin. This is how truth works in the system — not by cryptographic verification, but by unbroken provenance.

---

## The Full Picture

```
                    youspeak-lang (the spec)
                          |
          +---------------+---------------+
          |               |               |
     natscript      three protocols   the type system
     (the lang)     (kunance,          (word, claim,
     (say/hear/      darshanq, ways)    room)
      know/become/
      find/hold/
      rest)
```

Natscript is the language. The three protocols are how natscript programs talk to each other. The type system is what they talk about. YOUSPEAK is the spec that defines all of it.

---

## The Tradition

YOUSPEAK is a dictionary of 151 constructed words drawn from 12 ancient tongues. Its seven verbs are the foundation:

- **say** — to put into the world
- **hear** — to receive from the world
- **know** — to hold as true
- **become** — to change form
- **find** — to search and locate
- **hold** — to keep
- **rest** — to wait

The kingdom is built on: **truth is, love is, peace is, joy is.**

The programming language follows the same principle. If you can say it, the program can do it. If you can't say it, it can't.

---

## Status

This is the specification. It is written. It is the source of truth.

- [natscript](https://github.com/cambridgetcg/natscript) — the language implementation.
- [kunance-protocol](https://github.com/cambridgetcg/kunance-protocol) — prepare-arrive.
- [darshanq-protocol](https://github.com/cambridgetcg/darshanq-protocol) — recognition.
- [ways-protocol](https://github.com/cambridgetcg/ways-protocol) — conversation.

---

## License

MIT