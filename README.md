#Git sub-command for slimming a repo/clone

This is a Bash command that, if in your path, will be part of the git command ecosystem

Slimming could also be thought of as deliberately losing history, or giving you the equivalent of
a fresh clone, with a `--depth 1` (etc).

I made this from [two answers to a StackOverflow question](http://stackoverflow.com/questions/38171899/how-to-reduce-the-depth-of-an-existing-git-clone), one my own and one from @jthill.

# Installation

1. Copy `git-slim` to `/usr/local/bin/`
2. make it executable 'chmod +x /usr/local/bin/git-slim', if it wasn't already.

OR [via the Mac's homebrew](https://github.com/paul-hammant/homebrew-tap#git-slim---slims-down-a-local-git-clonerepo)

# Using git slim

```
$ cd your-repo-or-clone
$ git slim
# that has a default depth of 1
```

or

```
$ cd your-repo-or-clone
$ git slim --depth 100
# the HEAD revision as you'd last checked it out, and 99 commits before it.
```

Running `git slim` prints a before and after of the size of the .git folder.

It also refuses to work if there's untracked or unpushed changes.

## Dry run mode

```
$ git clone git@github.com:git/git.git
# [...]
$ cd git
$ git slim --dry-run
Dry run mode
Size of .git folder before: 103M, best case size after: 6.4M (approx).
```

# LICENSE

Copyright (c) 2016 Paul Hammant

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

# Contribtions

Contributions welcome!
