---
layout:     post
title:      "Useful Git configs"
date:       2017-11-16 16:40:00
summary:    "" 
categories: git
---

### Merge vs. Rebase
* Merge grabs the commits you're trying to merge and creates a new commit for it.
* Merges are nice because they are *non-destructive*.
* Rebase changes the history so that they line up at the correct places.
* Rebase gives you a much cleaner git history.
* See this link for useful images: [https://www.atlassian.com/git/tutorials/merging-vs-rebasing]

### Configure pull default for all branches
`git config --global pull.rebase true`  

### Reuse Record Resolution (ReReRe)
* Records all fixes to merge conflicts
* Reuses them automatically if the same conflict recurs  
`git config --global rerere.enabled true`  

### Colors
`git config --global color.ui true`
