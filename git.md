a*Rules for developers only*
# Keep commit history clean
* Clean history helps in understanding code via Blame tool
* Clean history helps in reviewing pull request

## Don't change git blame if possible
* Avoid to make unneccessary changes in code lines if possible
  * it saves from a situation when you need to find significant commit for specific line in codes, but Blame tool shows a commit that either updates indent or adds a space, semicolon, comma, etc.
  * it saves reviewer's time

## Use informative commit messages

### Tag commits
* Use [tags](https://gitlab.com/itpp/handbook/blob/master/documenting-updates.md) to specify commit type

### Use reference to an issue
* Use reference to corresponding issue if any, e.g. ``work on issue #123``
* If commit fixes/closes issue at github, use [special format](https://help.github.com/articles/closing-issues-using-keywords/) to close that issue after merging, e.g. ``close #123``

### Commit message has to give an idea of the update
* Don't use too short messages like "fix", "oops", "updates" etc
* Commit message must be about updates commit makes, i.e. about diff
  * Don't reference to something outside the code, e.g. following messages **are incorrect**:
    * *I'm going to switch from work computer to home computer, so I upload everything I have for now* -- use instead *[ADD] module for ...*
  * If you made commit squashing (e.g. via ``git rebase -i``), review your diff again and describe updates of *new* commits only
  * In the main, you cannot use the same commit message twice
* It must be clear from the commit message **why** do you make such changes, e.g. following messages are **not enough**:
  * *[FIX] move calling function A from function X to function Y* -- it's necessary to explain what it fixes, why it was wrong to put calling A to X, etc
  * [[FIX] change ' to " and add comma to end of the line](https://github.com/it-projects-llc/mail-addons/commit/4cf63ab4e2af57a69a025abff7e5a4a45d779338) -- guess why
* If commit fixes an error, don't just give a name to that error. Describe what error is. Examples of bad commit messages:
  * *[FIX] fix longpolling error* -- there could be a lot of different errors related to longpolling, you need to specify which one was in a code and fixed now

# Be careful about git merge
* Wrong usage of `git merge` can lead to [changes](https://github.com/it-projects-llc/misc-addons/pull/136) [lost](https://github.com/yelizariev/odoo-saas-tools/commit/2c17db7236f558911dbe91874d44c96b46250103) (mostly due to forgotten ``git fetch upstream`` or changed *strategy*)

## Avoid to change strategy in git merge
* Don't use `-s` option in `git merge`

## Don't rename merge commits
* use default merge message. You can add something there if needed, but don't delete default message
  * reviewer has to now which commits are merge commits
  * default merge message is used in multi pull requests

# Make PR clean

## Squash commits after work on reviews and CI checks

PR cannot have commits that fix other commits of the same pull request

# Avoid using of --force
* Use ``--force-with-lease`` instead of ``--force``

  * It prevents from losing updates made by reviewers directly in PR
  * If you get an error on doing  ``--force-with-lease``, it most likely that you have to do ``git fetch origin`` and ``git rebase origin/....``
