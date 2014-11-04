tagging-test
============

Empty Github repo created to test pushing a local repo up. Test whether local
tags are automatically configured as Github Releases.

Github New Repo Instructions
----------------------------

_My note: Replace `github.com` in the commands below with my local SSH alias
configured for this alternate Github testing account. Also, don't forget to
configure the local git repo to use the username and email for this alternate
account._

We recommend every repository include a README, LICENSE, and .gitignore.

### ...or create a new repository on the command line

```
touch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:test-8h6xtixg/tagging-test.git
git push -u origin master
```

### ...or push an existing repository from the command line

```
git remote add origin git@github.com:test-8h6xtixg/tagging-test.git
git push -u origin master
```

### ...or import code from another repository

You can initialize this repository with code from a Subversion, Mercurial, or
TFS project.


------------------------------------------------------------------------------

My Testing
----------

Tag the first commit so `git describe` will work:

```bash
$ git tag -a v0.0.0 -m 'Version 0.0.0 Alpha'

$ git show --pretty=fuller --stat --tags
```

Push tag to Github:

```bash
$ git push origin v0.0.0
Counting objects: 1, done.
Writing objects: 100% (1/1), 180 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To git@github-test:test-8h6xtixg/tagging-test.git
 * [new tag]         v0.0.0 -> v0.0.0
```

And yep, it does automatically show up as a release on Github. Just don't add
any release notes and it won't be formatted to look like a Github release. Note
that marking a tag as pre-release, adds the release formatting so I probably
don't want to do that. I had to poke around to find a way to delete the release
notes to get rid of that Github release formatting. Just deselecting the
pre-release checkbox didn't remove the formatting.
