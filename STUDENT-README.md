# Call Debrief

This installer adds the Call Debrief Claude Code Skill to your existing AI Workspace.

It turns one call transcript into a short debrief: what the call was about, how it actually went, what you committed to, what other people owe you, and what is still unresolved.

You will not need to open or move any hidden folders yourself.

## Install it

1. Download and unzip this folder.
2. Open your existing AI Builder Bootcamp AI Workspace in VS Code.
3. In VS Code, choose File, then Add Folder to Workspace.
4. Choose this unzipped Call Debrief Skill Installer folder.
5. Open Claude Code in the same VS Code window.
6. Type:

`Read INSTALL-ME.md from the Call Debrief Skill Installer folder and install the Skill exactly as written.`

7. Wait until Claude says: `Call Debrief Skill installed.`
8. Start a fresh Claude Code conversation.
9. Type: `/call-debrief`

## Before you run it

You need a transcript. Zoom, Fathom, Granola, Otter, or anything else that produces text.

Save it in `my-business/calls/` in your AI Workspace, or just paste it into the conversation.

## What you get

A debrief saved in `outputs/call-debriefs/` covering:

- What the call was about and where it landed
- An honest read on how it went
- What you committed to, with dates only where a date was actually said
- What other people committed to
- What is still open

## The problem this actually solves

The promise that costs you is never the one in the first five minutes. It is the one at minute fifty-two, after the real conversation is over and everyone is wrapping up, when you say "yeah, I'll send that over" and then never think about it again.

Nobody re-reads a sixty-minute transcript to find it. So it just quietly does not happen, and the other person notices.

## Two things it will not do

**It will not invent a commitment.** If the transcript is unclear about who owns something, it puts it under Still Open as a question instead of assigning it to someone. A wrong action item is worse than a missing one, because you would actually go do it.

**It does not treat "we should probably" as a promise.** Only things somebody actually committed to become action items.

## Notes

It reads your transcript and never changes it.

Do not upload passwords, login codes, financial account details, health information, or confidential client information. Call transcripts often contain more than you remember, so skim before you use one.
