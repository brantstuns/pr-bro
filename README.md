# pr-bro

![bro](http://i.giphy.com/OIEhvGRByVrHO.gif)

Pull request helper script for Javascript projects. This just makes sure your tests run before pushing and that you don't try any funny business with the master branch.

## INSTALL

Basically just clone this and run `ln -s ~/path/to/repo/pr-bro /usr/local/bin/pr-bro`.

---

#### _IMPORTANT_: *make sure and replace ~/path/to/repo/pr-bro above to the correct path to wherever you cloned the repo*.
##### You can test that the above worked by running:`which pr-bro`, which should return */usr/local/bin/pr-bro*

Make sure /usr/local/bin or $HOME/bin if you prefer is on your $PATH.

---


use it by running `pr-bro` in a git repo your about to open a PR with.

##### FOR NPM PROJECTS: run `pr-bro npm`

`pr-bro` alone will default to running `yarn test`, otherwise it will run `npm test` so make sure those scripts in your package.json run your full test suite and your linter


*NOTE:* This is pretty specialized to my current team and won't fit everyone's git flow. It's pretty generic but basically if you want to tailor it to work better for you edit that 
```perl
$test_command
``` 
variable to be whatever command your run for your tests. 

All the script does is

1. Check if you're on the master branch and if so prompt you for a name and checkout to a new local branch.
2. Run your tests and if all passes then push upstream to the new branch you just made.
3. Then you can go open your PR.
