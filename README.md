# Intro

Generate a pull requests report for GitHub release. like

```
Last release time is 8/14/2015 6:46:52 PM

New merged pull requests:
1. #1737 refactor(favicon): do not use querySelector by @L42y
2. #1736 fix search icon margin problem by @loddit
3. #1735 fix: channel switching shortcuts by @L42y
4. #1734 fix: cleanup NW leftover by @L42y
5. #1731 fix: scale image proportionally to fit in screen by @L42y
6. #1721 Snippet ext close #1705 by @loddit

```

It design for Pull Request Workflow


```
          +----------------------------------------------------+
          |+--------------------------------------+            |
          ||+---------+                           |            |
  Fork -> ||| Commits | -> Pull Requests -> Merge | -> Release |
          ||+---------+                           |            |
          |+--------------------------------------+            |
          +----------------------------------------------------+
```

Publish a Github release is a important part of our team(BearyInnovative)`s workflow. It happened before every deployment for prodution envivornment.

It benefits us quite a lot in these case:

  1. Rollback, Our CI tool can deploy code with a definite tag (release)
  2. Review, It help us to know the accurate time of features or bug fixes online

Legilimens help you generate release report with pull requests info


## Command Usage

1. Install packages
  `npm install`

2. Edit a config file in legilimens`s repo folder to setup GitHub account and repo

  `.config.json`

  ```
  {
    "token": // your github access token, see https://github.com/settings/tokens not needed for public repo
    "repo_path": // as github/hubut in https://github.com/github/hubot
    "repo_branch": // prs' base branch, eg: `master`
  }
  ```
  (Optinal, otherwise you need answer some interactive command questions later)

3. Run Script
  `npm start`

   Result

4. For Hofix
  `npm start [hotfix-branch-name]`

## Library Usage

```js
const legilimens = require('legilimens');

legilimens(token, repoPath, baseBranch, function(output) {
  ...
  your code here(use output)
  ...
});
```

# Legilimens

In Harry Potter`s Magic World, Legilimens is the spell used for the practice of Legilimency (OP24). Legilimens is presumably used non-verbally whenever someone uses the arts of Legilimency to obtain information. However, there may be subtler ways to do this.

More info at [Harry Potter Wiki](http://harrypotter.wikia.com/wiki/Legilimency_Spell)

@loddit 2015
