# ReleaseProof evaluation configuration

This fork exists to evaluate [ReleaseProof](https://github.com/ihsansengun/ReleaseProof)
on an application that was not written for it. Kanboard's code is as
upstream at commit `51d6e6f72d3f967ecbcbfff8ed38012613bb96ea`.

| File | Purpose |
|---|---|
| `../releaseproof.yml` | How to build and start Kanboard for a test run, the account a new installation has, where it may write |
| `Dockerfile` | Test image: Kanboard's own Alpine and PHP packages, PHP's built-in server, one unprivileged process |
| `authority.yml` | Who may state or amend requirements |

Nothing here is read by Kanboard. No workflow and no credential is added to
this repository: runs are started from ReleaseProof's own repository, which
holds the credentials and fetches a pull request of this fork as data.

A pull request on the branch `releaseproof/verify-only` exists only to give free verification runs a commit to build. It is never merged.
