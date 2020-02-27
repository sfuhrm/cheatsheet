### Git VCS Cheat Sheet

#### Clone / push
* Getting a remote repo<br/>
  `git clone $URL`
* Pushing commits to remote<br/>
  `git push $REMOTE`

#### Showing differences

* Differences to HEAD<br/>
  `git diff`
* Differences to a branch<br/>
  `git diff $BRANCHNAME`
* Differences of one commit<br/>
  `git diff $COMMITHASH^ $COMMITHASH`

#### Branches

* Adding a branch<br/>
  `git branch $BRANCHNAME`
* Switchting to a branch<br/>
  `git checkout $BRANCHNAME`

#### Tags
* Adding a tag<br/>
  `git tag $TAGNAME`

* Deleting a tag<br/>
  `git tag -d $TAGNAME`

* Deleting a remote tag<br/>
  `git push --delete origin $TAGNAME`

#### Merging
* Merging a branch into the current<br/>
  `git merge $BRANCHNAME`
* Cherry-picking a single commit into the current branch<br/>
  `git cherry-pick $COMMITHASH`
