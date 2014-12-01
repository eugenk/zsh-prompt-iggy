# iggy
iggy is a super happy awesome Powerline-style, Git-aware prezto theme.
[Prezto](https://github.com/sorin-ionescu/prezto) and its [`git` module](https://github.com/sorin-ionescu/prezto/tree/master/modules/git) are required to use this.
Also, you need a powerline patched font. I recommend picking one of these:
* https://gist.github.com/qrush/1595572
* https://github.com/Lokaltog/powerline-fonts

I, myself, use mensch-Powerline.

![screen shot 2014-11-15 at 17 37 19](https://cloud.githubusercontent.com/assets/339751/5249189/76a966e8-7981-11e4-8279-39dacc78adb8.png)

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
  * `?` if there are untracked files
  * `✚` if there are added files in the staging area
  * `✖` if there are deleted files in the staging area
  * `➙` if there are renamed/moved files in the staging area
  * `✱` if there are modified files in the staging area
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

## More Screenshots
![screen shot 2014-11-15 at 17 37 19_annotated](https://cloud.githubusercontent.com/assets/339751/5249199/81bc5306-7981-11e4-8005-69e55b3bf3ba.png)
![screen shot 2014-11-15 at 17 54 58](https://cloud.githubusercontent.com/assets/339751/5249192/79ba5112-7981-11e4-89cf-8c294e701c54.png)
![screen shot 2014-11-15 at 18 05 06](https://cloud.githubusercontent.com/assets/339751/5249196/7df0043e-7981-11e4-92e4-f9fd62917ff4.png)
