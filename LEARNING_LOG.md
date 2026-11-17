# Learning Log — Project 1: Backgammon

## About me

Self-ratings from the interview (1 = never, 5 = regularly):

| Area | Rating |
|---|---|
| Terminal / command line | 3 |
| Writing code | 3 |
| Git / GitHub | 3 |
| AI tools | 4 |
| Product / business (requirements, projects, customers) | 5 |

- On a Mac.
- Strong product instincts: cut scope quickly and reasoned about tradeoffs well.
- Code reading is the area to keep building: predictions were good on logic (loops, dice state), shakier on reading syntax cold.
- Prefers to keep moving; often skipped explain-backs when short on time.

---

## Terminal
**My words:** A text-based window you type directions for the computer into. Developers still use it because text can be sent around easily, is interpretable, and is the same for everyone.
**Added:** Text commands can be repeated and automated, and most servers have no screen at all.
**Business equivalent:** A documented process versus "watch me do it." Only one of them scales.

## File and folder
**My words (corrected):** `pwd` gives the full address of where I am (country › state › city › street). `ls` lists what's inside. `..` means one level *up*, the folder that contains this one.
**Business equivalent:** An org chart. `..` is "who do I report to."

## State
**My words (corrected):** The facts the program is tracking right now. After rolling a 3 and 5, `rolled` becomes `true` and `movesLeft` becomes `[3, 5]`: two separate dice, not their sum. A double 4 becomes `[4, 4, 4, 4]`.
**Business equivalent:** Two separately approved budget lines versus one lump sum. Keeping them separate lets you check each against its own rule.

## If statement
**My words:** A rule with a condition: if this is true, do that. In the game: if exactly one opponent checker is on the landing point, send it to the bar.
**Business equivalent (mine):** If the customer buys this product, then their automatic 5-year warranty starts.

## Loop
**My words:** Repeating the same steps many times. `allHome` checks all 24 points one by one. If it only checked 12, checkers in the outer board would be missed and you could bear off before everything was home.
**Business equivalent:** Running payroll: for each employee, calculate pay.

## Git
**My words:** Without version history, mistakes kill momentum because you can't find them. History lets you restore from a working place.
**Business equivalent:** Signing the statement of work before the contractor starts, so there's a record of what was agreed.

## Commit and commit history
A **commit** is a save point (a snapshot of the files). The **commit history** is the list of them (`git log`). We committed the spec *before* the game existed so there's a clean starting point and a timestamp on what we agreed to.

## Repository (repo)
A folder git tracks. The history lives in the hidden `.git` folder.

## Acceptance criteria
**My words:** Agreements made before building a product that can be checked.
**Harder question: why do they matter more with an AI builder?** Because the agent doesn't know what's right or wrong for the build. Criteria let you check quickly whether it actually works. (Added: agents fill gaps with confident guesses and then say "done.")
**At work:** PMs write them on Jira/Linear tickets; QA and the PM check against them. Also called "definition of done."

## Spec / ticket / prompt
The same skill in three settings: a written description of what to build and what "done" means. On a team it's a ticket or spec; written for an AI, it's a prompt. Our `SPEC.md` became the subagent's brief.

## Bug and debugging
**My words (corrected):** A **bug** is a mistake in the code. The **error message** is the browser's description of it, including the line number. The **console** is the hidden browser panel where it shows up (Cmd + Option + J in Chrome). **Debugging** is finding and fixing it. The first bug was a typo (`rendr` for `render`); the fix was to correct the name, not add a new function.
**When to use `git restore` instead:** when you can't tell which change broke things. It rewinds to the last commit, but it also throws away any good changes made since then.
**Business equivalent:** Reconciling the books: the mismatch report tells you where to look; restoring from last month's close is the fallback.

## Agent and subagent
An **agent** is an AI that acts (edits files, runs commands), not just chats. A **subagent** is an agent started by another agent to do one job, with its own fresh memory. It only knows its brief.
**Business equivalent:** A senior banker handing the DCF build to an analyst, then reviewing it before it goes to the client.

## Context window
**My words:** Use a subagent to build to save memory.
**Added:** The context window is the agent's working memory for a conversation. The subagent's 370 lines of work filled *its* window; only a short report came back. Handoffs still cost something (brief, rereading, checking), so small jobs are done directly.

## Adversarial review and QA
**Not yet done.** The reviewer subagent has run; its findings are sealed until I test the spec myself (see "Still to do").

## Permission modes and sandboxes
Modes range from Manual (ask before everything) to Accept edits, Plan, and Auto. A **sandbox** is a boundary the computer enforces on which files and sites the agent can reach. It's safer than approving by hand because people stop reading requests after the fiftieth.
**Business equivalent:** A new hire's expenses are all reviewed at first; later they get a company card with a limit. The limit is what makes it safe to stop reviewing receipts.

---

## Terminal commands cheat sheet

| Command | What it does |
|---|---|
| `pwd` | Print the folder you're in |
| `ls` / `ls -la` / `ls ..` | List this folder / including hidden files / the folder above |
| `cd folder` / `cd ..` | Move into a folder / up one |
| `nano file` | Edit in the terminal (Ctrl+W search, Ctrl+O save, Ctrl+X exit) |
| `open file` | Open with the default Mac app |
| `git init` | Start tracking this folder |
| `git status` | What changed since the last commit |
| `git add file` | Stage a file for the next commit |
| `git commit -m "msg"` | Make a commit |
| `git log --oneline` | Show commit history |
| `git diff` | Show exact changes since the last commit |
| `git restore file` | Discard changes since the last commit (not undoable) |

## Things I still don't get
- What the console is and when to open it (partly cleared up above)
- Wanted a fuller list of terminal commands

## Still to do
- **Stage 7:** play the game and mark each acceptance criterion in `SPEC.md` Pass / Fail / Couldn't test. Then go through the reviewer subagent's findings one at a time, testing each before hearing whether it's right. Then explain back using "QA" and "adversarial review."
