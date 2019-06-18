# Personal fork of nnn

I forked jarun's [nnn](https://github.com/jarun/nnn), so that I can
incorporate my own keybindings, while still being able to update `nnn`.
I do it this way, since keybindings are defined at compile time
in `nnn.h`.

## Setup

I performed the following steps to set this up on a new PC.

* `git clone https://github.com/brambozz/nnn`
* `git remote add upstream https://github.com/jarun/nnn`

For updating `nnn`, I do the following:

* Find the commit hash `#` for the desired new version
* `git fetch upstream`
* `git merge #`
* Fix any merge conflicts in `nnn.h`

The finally, build `nnn`:

```
make clean
make 
sudo make install
```

## Dependencies

There are a number of dependencies for my use:
```
vidir
```

## Custom keybindings

Since I use Colemak as keyboard layout and have some custom bindings
in vim, I try to make the two coherent. Below is copied from the
original readme, but changed with my bindings.
At some point, I want to make a cheatsheet for this.
I have tried to make it compatible with my nvim stuff, by using
small letters as much as possible and otherwise capital letters.  

```
 NAVIGATION
          ↑ e  Up          PgUp ^E  Scroll up
          ↓ n  Down        PgDn ^N  Scroll down
          ← o  Parent dir        ~  Go HOME
        ↵ → i  Open file/dir     @  Start dir
    Home g ^A  First entry       -  Last visited dir
     End G     Last entry        .  Toggle show hidden
            /  Filter       Ins ^T  Toggle nav-as-you-type
            b  Pin current dir  ^B  Go to pinned dir
       Tab ^I  Next context      d  Toggle detail view
         , ^/  Leader key  N LeadN  Enter context N
          Esc  Exit prompt      ^L  Redraw/clear prompt
           ^Q  Quit and cd       q  Quit context
            Q  Quit              ?  Help, config
 FILES
            O  Open with...      N  Create new/link
            D  File details      R  Rename entry
    ⎵ ^K /  V  Select entry/all  r  Batch rename
            v  Toggle selection  l  List selection
            y  Copy selection    x  Delete selection
            p  Move selection    X  Delete entry
            f  Create archive  m M  Brief/full mediainfo
           ^F  Extract archive   F  List archive
            E  Edit in EDITOR    P  Open in PAGER
 ORDER TOGGLES
           ^J  Disk usage        S  Apparent du
           ^W  Random  s  Size   t  Time modified
 MISC
         ! ^]  Spawn SHELL       C  Execute entry
         ^R  Run/pick script   L  Lock terminal
           ^P  Prompt  ^N  Note  =  Launcher
```
