# Contributing to GitCourse

It is warmly welcomed if you have interest to hack on GitCourse. First, we encourage this kind of willing very much. And here is a list of contributing guide for you.

## Topics

* [Reporting issues](#reporting-general-issues)
* [Code and doc contribution](#code-and-doc-contribution)
* [Test case contribution](#test-case-contribution)
* [Engage to help anything](#engage-to-help-anything)

## Reporting general issues

To be honest, we regard every user of GitCourse as a very kind contributor. After experiencing GitCourse, you may have some feedback for the project. Then feel free to open an issue via [NEW ISSUE](https://github.com/kfcoding/gitcourse/issues/new).

Since we collaborate project GitCourse in a distributed way, we appreciate **WELL-WRITTEN**, **DETAILED**, **EXPLICIT** issue reports. To make the communication more efficient, we wish everyone could search if your issue is an existing one in the searching list. If you find it existing, please add your details in comments under the existing issue instead of opening a brand new one.

To make the issue details as standard as possible, we setup an [ISSUE TEMPLATE](./.github/ISSUE_TEMPLATE.md) for issue reporters. Please **BE SURE** to follow the instructions to fill fields in template.

There are a lot of cases when you could open an issue:

* bug report
* feature request
* performance issues
* feature design
* help wanted
* doc incomplete
* test improvement
* any questions on project
* and so on

Also we must remind that when filling a new issue, please remember to remove the sensitive data from your post. Sensitive data could be password, secret key, network locations, private business data and so on.

## Code and doc contribution

Every action to make project GitCourse better is encouraged. On GitHub, every improvement for GitCourse could be via a PR (short for pull request).

* If you find a typo, try to fix it!
* If you find a bug, try to fix it!
* If you find some redundant codes, try to remove them!
* If you find some test cases missing, try to add them!
* If you could enhance a feature, please **DO NOT** hesitate!
* If you find code implicit, try to add comments to make it clear!
* If you find code ugly, try to refactor that!
* If you can help to improve documents, it could not be better!
* If you find document incorrect, just do it and fix that!
* ...

Actually it is impossible to list them completely. Just remember one principle:

> WE ARE LOOKING FORWARD TO ANY PR FROM YOU.

Since you are ready to improve GitCourse with a PR, we suggest you could take a look at the PR rules here.

* [Workspace Preparation](#workspace-preparation)
* [Branch Definition](#branch-definition)
* [Commit Rules](#commit-rules)
* [PR Description](#pr-description)

### Workspace Preparation

To put forward a PR, we assume you have registered a GitHub ID. Then you could finish the preparation in the following steps:

1. **FORK** GitCourse to your repository. To make this work, you just need to click the button Fork in right-left of [kfcoding/gitcourse](https://github.com/kfcoding/gitcourse) main page. Then you will end up with your repository in `https://github.com/<your-username>/gitcourse`, in which `your-username` is your GitHub username.

1. **CLONE** your own repository to develop locally. Use `git clone https://github.com/<your-username>/gitcourse.git` to clone repository to your local machine. Then you can create new branches to finish the change you wish to make.

1. **Set Remote** upstream to be `https://github.com/kfcoding/gitcourse.git` using the following two commands:

```
git remote add upstream https://github.com/kfcoding/gitcourse.git
git remote set-url --push upstream no-pushing
```

With this remote setting, you can check your git remote configuration like this:

```
$ git remote -v
origin     https://github.com/<your-username>/gitcourse.git (fetch)
origin     https://github.com/<your-username>/gitcourse.git (push)
upstream   https://github.com/kfcoding/gitcourse.git (fetch)
upstream   no-pushing (push)
```

Adding this, we can easily synchronize local branches with upstream branches.

### Branch Definition

Right now we assume every contribution via pull request is for [branch master](https://github.com/kfcoding/gitcourse/tree/master) in GitCourse. Before contributing, be aware of branch definition would help a lot.

As a contributor, keep in mind again that every contribution via pull request is for branch master. While in project GitCourse, there are several other branches, we generally call them rc (release candidate) branches, release branches and backport branches.

Before officially releasing a version, we will checkout a rc branch. In this branch, we will test more than branch master.

When officially releasing a version, there will be a release branch before tagging. After tagging, we will delete the release branch.

When backporting some fixes to existing released version, we will checkout backport branches. After backporting, the backporting effects will be in PATCH number in MAJOR.MINOR.PATCH of [SemVer](http://semver.org/).

### Commit Rules

Actually in GitCourse, we take three rules serious when committing:

* [Commit Message](#commit-message)
* [Sign your work](#sign-your-work)

#### Commit Message

Commit message could help reviewers better understand what is the purpose of submitted PR. It could help accelerate the code review procedure as well. We encourage contributors to use **EXPLICIT** commit message rather than ambiguous message. In general, we advocate the following commit message type:

* docs: xxxx. For example, "docs: add docs about terminal".
* feat: xxxx.For example, "feat: make result show in sorted order".
* bugfix: xxxx. For example, "bugfix: fix param check".
* refactor: xxxx. For example, "refactor: simplify to make codes more readable".
* test: xxx. For example, "test: add unit test case for func InsertIntoArray".
* other readable and explicit expression ways.

On the other side, we discourage contributors from committing message like the following ways:

* ~~fix bug~~
* ~~update~~
* ~~add doc~~

If you get lost, please see [How to Write a Git Commit Message](http://chris.beams.io/posts/git-commit/) for a start.

#### Sign your work

The sign-off is a simple line at the end of the explanation for the patch, which certifies that you wrote it or otherwise have the right to pass it on as an open-source patch.
The rules are pretty simple: if you can certify the below (from [developercertificate.org](http://developercertificate.org/)):

```
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.
660 York Street, Suite 102,
San Francisco, CA 94110 USA

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.

Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

Then you just add a line to every git commit message:

```
Signed-off-by: Joe Smith <joe.smith@email.com>
```

Use your real name (sorry, no pseudonyms or anonymous contributions.)

If you set your `user.name` and `user.email` git configs, you can sign your commit automatically with `git commit -s`.

### PR Description

PR is the only way to make change to GitCourse project files. To help reviewers better get your purpose, PR description could not be too detailed. We encourage contributors to follow the [PR template](./.github/PULL_REQUEST_TEMPLATE.md) to finish the pull request.

## Test case contribution

> TODO: Will be filled after we have a test framework

## Engage to help anything

We choose GitHub as the primary place for GitCourse to collaborate. So the latest updates of GitCourse are always here. Although contributions via PR is an explicit way to help, we still call for any other ways.

* reply to other's issues if you could;
* help solve other user's problems;
* help review other's PR design;
* help review other's codes in PR;
* discuss about GitCourse to make things clearer;
* advocate GitCourse technology beyond GitHub;
* write blogs on GitCourse and so on.

In a word, **ANY HELP IS CONTRIBUTION.**
