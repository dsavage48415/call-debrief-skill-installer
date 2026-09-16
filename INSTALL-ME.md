# Install Call Debrief

You are installing one approved AI Builder Bootcamp Claude Code Skill into the student's existing AI Workspace.

Your only job is to copy the supplied Skill into the correct runnable and backup locations, verify the installation, and stop.

## How to communicate

- Use plain language.
- Keep messages short.
- Never use developer jargon.
- Never use em dashes.
- Use AI Workspace, never AI Workshop.
- Do not teach the Skill or begin using it during installation.

## Never use Terminal or helper agents

Use only file reading, writing, editing, and file search tools.

Never run Bash, Terminal, shell commands, scripts, or operating-system commands.

Never launch a helper agent or subagent. A helper agent may ignore these installation boundaries.

## Step 1: Find the installer and the AI Workspace

Use file search to locate the installer source:

`call-debrief/SKILL.md`


Then locate the student's AI Builder Bootcamp Starter Workspace. It must contain all of these paths in the same top-level folder:

- `START-HERE.md`
- `my-business/`
- `workflows/`
- `outputs/`
- `.claude/skills/`
- `_system/skills-backup/`

If you cannot identify exactly one valid installer source and exactly one valid AI Workspace, do not write anything. Tell the student which folder is missing and stop.

## Step 2: Explain the installation

Say:

"I found the Call Debrief Skill installer and your AI Workspace.

I am going to add one new Claude Code Skill in 2 matching locations: the runnable Skill folder and its backup. I will not change your business files, workflows, outputs, or existing Skills."

Then continue without asking the student to manage hidden folders.

## Step 3: Check for an existing copy

Check these destination paths inside the AI Workspace:

- `.claude/skills/call-debrief/`
- `_system/skills-backup/call-debrief/`

If neither exists, continue.

If either exists, do not overwrite it automatically. Tell the student the Skill is already installed and ask whether they want to replace it with this approved v1 copy.

If they say no, stop.

If they say yes, preserve the full existing runnable and backup contents under:

`_system/skills-backup/call-debrief-history-YYYY-MM-DD/`

If that history folder exists, add `-2`, then `-3`, until the name is unused.

Only then replace the existing copy.

## Step 4: Copy the approved Skill

Copy the complete installer source into both destinations.

Runnable copy:

- `.claude/skills/call-debrief/SKILL.md`

Backup copy:

- `_system/skills-backup/call-debrief/SKILL.md`

Do not change the supplied file contents.

Do not write to my-business, workflows, outputs, START-HERE.md, or any existing Skill.

## Step 5: Verify the installation

Read every file in both destinations.

Confirm:

1. All 2 destination files exist and are not empty.
2. The runnable and backup SKILL.md files match exactly.
3. Each runnable reference matches its backup exactly.
4. The Skill frontmatter contains:
   - `name: call-debrief`
   - `disable-model-invocation: true`
   - `user-invocable: true`
   - `allowed-tools: Read, Write, Edit, Glob, Grep`
5. The Skill contains the command `/call-debrief`.

If anything fails, fix only the failed installation item and verify again.

## Completion message

Only after every verification passes, say:

"Call Debrief Skill installed.

Start a fresh Claude Code conversation inside this AI Workspace and type:

/call-debrief

You can now remove the Call Debrief Skill Installer folder from the VS Code workspace. Do not delete your AI Workspace."

If verification does not pass, do not claim installation is complete.
