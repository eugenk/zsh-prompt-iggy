# iggy
iggy is a super happy awesome Powerline-style, Git-aware prezto theme.
[Prezto](https://github.com/sorin-ionescu/prezto) and its [`git` module](https://github.com/sorin-ionescu/prezto/tree/master/modules/git) are required to use this.
Also, you need a powerline patched font. I recommend picking one of these:
* https://gist.github.com/qrush/1595572
* https://github.com/Lokaltog/powerline-fonts

I, myself, use Menlo-Powerline.

![zsh-prompt-iggy](https://cloud.githubusercontent.com/assets/339751/7430923/37b81b32-f019-11e4-9ea9-24716c619e1d.png)


## Features
The status line is divided into many colored segments:
* Status segment
  * A red cross (✘) indicates an exit code different from 0 (last command unsuccessful)
  * A green lightning (⚡) indicates super powers
  * A blue percent-symbol (﹪) shows that there are background jobs
* Current working directory
  * Abbreviated path - only the last directory in the path is fully qualified
  * Red background if you have no write access to the current working directory
* User@host
  * Only shown if
    * Another user than the `$default_user` is logged in
    * Or if you are connected via SSH
* Git status
  * Colors
    * green: clean working copy
    * yellow: you have a stash
    * red: the working copy is dirty
  * Current git branch or commit
  * `?2` if there are 2 untracked files/directories in the working copy
  * `✚` if there are added files in the staging area
  * `✖` if there are deleted files in the staging area
  * `✖5` if there are 5 deleted files not yet staged
  * `➙` if there are renamed/moved files in the staging area
  * `✱` if there are modified files in the staging area
  * `✱2` if there are 2 modified files not yet staged
  * `⬆ 3` if you have 3 commits that are not on the remote
  * `⬇ 5` if there are 5 commits on the remote that you don't have
  * `s7` if you stashed 7 times
  * some more information in rebase, merge and so on...
* Git subdirectory
  * If you are in a git working copy, the current working directory is split into two parts:
    The path of the working copy and the path relative to it.
    The former is displayed in the "Current working directory" segment in the abovementioned abbreviated form while the latter is displayed in the gray git directory segment to the right of the git status.

Also, you have the current date and time in the right prompt.

The arrowhead symbol in the second line is colored depending on the state:
* orange-ish: normal color
* red: last exit code was not 0
* green: you have super powers

## Installation
Make sure, that your terminal is running with 256 colors support. Some terminals support setting this in their preferences, like iterm2 for OS X. The default terminal for Gnome, for example, has no such option. There, you need to set `TERM=xterm-256color` in your `~/.zshrc`.

Simply copy the prompt_iggy_setup to `~/.zprezto/modules/prompt/functions/`.
Edit your `~/.zpreztorc` changing
```
zstyle ':prezto:module:prompt' theme 'your_current_theme'
```
to
```
zstyle ':prezto:module:prompt' theme 'iggy'
```

## Configuration
In your `~/.zshrc`, add
```
default_user=eugenk
```
but pick your own username ;)

If you don't set this variable, the user@host segment is only displayed, if you are connected via SSH.
