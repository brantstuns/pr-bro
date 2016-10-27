# pr-bro

![bro](http://i.giphy.com/OIEhvGRByVrHO.gif)

Pull request helper script. Basically just makes sure your tests run before pushing and that you don't try any funny business with the master branch.

**INSTALLATION**
Basically just clone this and from the repo run `ln -s ./pr-bro /usr/local/bin/pr-bro`.

Make sure /usr/local/bin or $HOME/bin if you prefer is on your $PATH.


use it by running `pr-bro` in a git repo your about to open a PR with.


*NOTE:* This is pretty specialized to my current team and won't fit everyone's git flow. It's pretty generic but basically if you want to tailor it to work better for you edit that 
```perl
$test_command
``` 
variable to be whatever command your run for your tests. 

All the script does is

1. Check if you're on the master branch and if so prompt you for a name and checkout to a new local branch.
2. Run your tests and if all passes then push upstream to the new branch you just made.
3. Then you can go open your PR.
