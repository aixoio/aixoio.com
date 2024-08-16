---
title: "How I made ZSH load 10 times faster"
pubDate: 2024-08-16
---

For a while now, my ZSH shell would take at least 10 seconds to open,
after a while of trying to find the source of this problem. I found it,
and I hate myself for it.

## The Problem

Every start up of a zsh shell would take 10 seconds including in TMUX,
and iTerm2. I am sure I have spent over 5 minues total waiting on a black
screen for a new shell to open.

## The Fix

After a while of this I tried to switch to FISH, to start with this I looked
in my `.zshrc` config, in that file it executes `zprofile` and in my `.zprofile`
is over **3,000 lines** of

```sh
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Remove this was easy thanks to Neovim. I just wrote one Regex and it was gone,
my `.zprofile` now only has one 


```sh
eval "$(/opt/homebrew/bin/brew shellenv)"
```

and will not be getting any more.

Thanks for reading.
