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
make 
sudo make install
```

## Custom keybindings
