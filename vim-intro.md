---
title: Vim Basics
layout: default
nav_order: 6
---

# Vim Basics for Git Users

Sooner or later, git is going to drop you into a text editor you didn't ask for. You'll run `git commit` without the `-m` flag, or git will need you to confirm a merge message during conflict resolution, and you're in an unintuitive and minimalist interface.

**vim** is git's default on almost every system.


## Why git uses vim

Vim is everywhere. It comes installed on essentially every Unix-like system — Linux servers, macOS, the WSL terminal on Windows. Git was written by Linux developers for whom vim was already the standard editor, so it became git's default for any operation that needs you to type more than a line.

You'll meet vim through git when you:

- Run `git commit` without `-m "message"` (git opens vim for the commit message)
- Run `git commit --amend` without `-m`
- Finish a merge — `git commit` after resolving conflicts opens vim
- Do an interactive rebase with `git rebase -i`
- Write a tag message with `git tag -a v1.0`


---

## Vim has modes

In a normal editor, typing letters inserts those letters. In vim, typing letters does that *only sometimes*. The rest of the time, letters are commands.

Two modes matter for survival:

- **Normal mode** — the mode you start in. Letters are commands. Pressing `i` doesn't type the letter "i"; it switches you to insert mode.
- **Insert mode** — behaves like a normal text editor. Letters insert letters.

You switch between them constantly:

- **Normal → Insert:** press `i`
- **Insert → Normal:** press `Esc`

If you're ever confused or feel stuck, press Esc. You're now in normal mode and can give commands.


## How to use vim with Git

When git drops you into vim for a commit message, here's the entire workflow:

1. **Press `i`** — switches to insert mode. Now you can type.
2. **Type your commit message** like you would in any editor.
3. **Press `Esc`** — switches back to normal mode.
4. **Type `:wq`** — colon means "I'm giving a command", `w` means "write" (save), `q` means "quit". Press Enter.
5. Done. You're back at the terminal, and git has your message.

If you want to bail out without saving — say you ran `git commit` by accident:

- Press `Esc`
- Type `:q!` and press Enter. The `!` means "force, don't save." Git will see an empty message and abort the commit.

That's it. With these five commands you can handle every situation git will throw at you.



## A practical run-through

```bash
echo "test" > test.txt
git add test.txt
git commit
```

Vim opens. You'll see something like:

```


# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
```

Now:

1. Press `i` — the bottom of the screen now says `-- INSERT --`
2. Type: `Test commit message`
3. Press `Esc` — `-- INSERT --` disappears
4. Type `:wq` and press Enter

You're back at the prompt. Run `git log --oneline` and your message is there.

---

## Some additional commands



| Key | What it does |
|---|---|
| `a` | Insert mode, cursor placed **after** the current character |
| `o` | Insert mode on a new line **below** the current one |
| `dd` | Delete the entire current line (normal mode) |
| `u` | Undo (normal mode) |
| `:w` | Save without quitting |
| `:q` | Quit (only if nothing has changed) |

You can ignore all of these and just use the five-step recipe above. You're not training to be a vim power user; you just want to commit your code.


## If you really hate it: change the default

If vim is more friction than you want, point git at a different editor. You only need to do this once:

```bash
git config --global core.editor "nano"
```

Other options:

- `"nano"` — friendly terminal editor; on-screen help at the bottom
- `"code --wait"` — VS Code (the `--wait` flag is essential; without it, git won't know when you're done)
- `"subl -n -w"` — Sublime Text
- `"micro"` — modern, modeless terminal editor

Honestly though: learning the five vim commands above takes about ten minutes, and vim is the one editor you can rely on being installed everywhere — on a colleague's laptop, on a remote server, in a recovered system. It's worth the small investment.

---

## Cheat sheet

Tape this to your monitor for the first week:

| What you want | Keys |
|---|---|
| Start typing | `i` |
| Stop typing (back to commands) | `Esc` |
| Save and quit | `:wq` then Enter |
| Quit without saving | `:q!` then Enter |
| Undo (in normal mode) | `u` |
| Delete the current line (in normal mode) | `dd` |

That's all you need. Vim has thousands of features and people make careers out of mastering them — but for git, the commands above will carry you through every situation you'll actually encounter.
