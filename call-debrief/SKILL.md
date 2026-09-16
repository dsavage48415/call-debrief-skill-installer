---
name: call-debrief
description: Turn one call or meeting transcript into a debrief the student can act on. Produces a summary, an honest read on how the call went, what the student committed to, what other people owe them, and what is still unresolved. Use only when the student manually types /call-debrief. Never invents a commitment nobody made. (v1, 2026-08-28)
disable-model-invocation: true
user-invocable: true
allowed-tools: Read, Write, Edit, Glob, Grep
---

# Call Debrief (v1, 2026-08-28)

Turn one call transcript into a debrief the student can act on, so nothing they promised on that call quietly falls through.

The reason this Skill exists: transcripts are long and the promises buried inside them are easy to miss. Somebody says "yeah, I'll get that over to you Thursday" at minute fifty-two and nobody ever reads that far again.

## How to communicate

- Use plain language for a non-technical business owner.
- Keep messages short.
- Never use developer jargon.
- Never use em dashes.
- Use AI Workspace, never AI Workshop.

## What good looks like

The student reads the debrief in ninety seconds and knows: what the call was about, whether it went well, what they owe and by when, what other people owe them, and what is still hanging.

It fails when it lists everything anyone said, or restates the transcript in a longer form. Fewer and sharper beats complete every time.

## Step 1: Get the transcript

The student gives you the transcript one of two ways.

**They point at a file.** Look in `my-business/calls/` inside the AI Workspace. If that folder does not exist, ask where the file is. If more than one file plausibly matches what they named, show the candidates and ask which one rather than guessing.

**They paste it into the chat.** Use what is in the message.

Do not proceed without a transcript. If you cannot find the file they named, say so and list what is actually there. Never write a debrief for a call you have not read.

If the transcript has a header listing who attended and when, read it. Knowing who was on the call is what lets you assign commitments to the right person.

## Step 2: Read the whole thing

Read the entire transcript before writing anything.

Skimming produces debriefs that miss the commitment at minute fifty-two, which is the exact failure this Skill exists to prevent.

As you read, hold four questions:

**What was this call for, and did it get there?** The stated purpose and what actually happened are often different. Say which.

**How did it feel?** Tone, energy, friction, enthusiasm, hesitation. This matters more than a label like "positive". A call can be perfectly pleasant and still tell you something is wrong.

**Who said they would do what?** Separate real commitments ("I'll send that Thursday") from things merely discussed ("we should probably look at that sometime"). Only real commitments become action items.

**What is unresolved?** Open questions, decisions pushed to later, things that need doing that nobody claimed.

## Careful with who said what

Automatic transcripts get speaker labels wrong, sometimes for long stretches.

Assign commitments based on what the words actually say, not the name printed above them. If the labels look unreliable, say so in the debrief rather than confidently attributing a promise to the wrong person.

## Step 3: Write the debrief

Save to `outputs/call-debriefs/YYYY-MM-DD-<short-call-name>.md` inside the AI Workspace. Create the folder if it is not there yet.

Ask the student for today's date if you are not sure of it.

Use this shape:

```
# Call Debrief: <call name>

**Date of call:** YYYY-MM-DD
**Who was there:** <names>

## Summary
Two to four sentences. What the call was about, what got decided, where it landed.

## How it went
A direct read in a sentence or two. Name the tone and what drove it. If there was friction, hesitation, or something left unsaid, say that.

## What I committed to
- [ ] <Start with a verb. What to do.> Due <date, only if a date was actually said>. <One line of context on why.>

## What other people committed to
**<Name>**
- <What they said they would do, and by when if they said.>

## Still open
- <Decisions not made, questions nobody answered, things parked for next time.>
```

Leave out any section with nothing in it rather than writing "None". An empty heading is noise. If nobody committed to anything at all, say that in one line under Summary.

### Writing the action items

**Titles are commitments, not topics.** "Send Dana the pricing sheet" tells the student what to do. "Pricing discussion" does not. Start with a verb.

**Only put a date on it if a date was actually said.** If someone said "by Friday" or "before the workshop", work out the real date from the call date and use it. If no date came up, leave it off. Inventing deadlines makes the list lie about what is urgent, and a list that lies gets ignored.

**Carry the context.** One line on why it matters. A title on its own loses the reason a week later.

## Step 4: Report back

Tell the student in the chat: what the call was, the one-line read on how it went, how many things they committed to, and how many things other people owe them.

They should not have to open the file to know what came out of it.

## Guardrails

**Never invent a commitment.** If the transcript is unclear about who owns something, put it under Still Open as a question rather than assigning it. A wrong action item costs more than a missing one, because the student will act on it.

**Hypotheticals are not commitments.** "We could maybe do a webinar sometime" is not a promise. Wait for the call where somebody actually says they will.

**Never use em dashes anywhere in the output.** This applies to every line, including the context clauses where an em dash feels natural. Write "Send the deck. She needs it before Thursday." not "Send the deck, she needs it before Thursday". Search the debrief for the character before you save it.

**Do not edit the transcript.** Read it, never change it.
