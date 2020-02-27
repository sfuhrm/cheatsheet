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

#### Configuration

* Setting the user name for commits<br/>
  `git config --global user.name "John Doe"`
* Setting the email address for commits<br/>
  `git config --global user.email johndoe@example.com`
* Setting the text editor for editing commits<br/>
  `git config --global core.editor emacs`
* Store the repository credentials for 15 minutes ([more](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage))<br/>
  `git config --global credential.helper cache`
* Store the repository credentials as plaintext, forever ([more](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage))<br/>
  `git config --global credential.helper 'store --file ~/.git-credentials'`
* Force GPG signature on tags (will work with Maven release to have signed releases in Github!) ([more](https://git-scm.com/docs/git-config/2.9.3#git-config-tagforceSignAnnotated))<br/>
  `git config --global tag.forceSignAnnotated true`
* Enable colors in Git output<br/>
  `git config --global color.ui auto`
