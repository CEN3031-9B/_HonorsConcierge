This repo contains 6 types of branchs. In order of decreasing stability:
 - master (stable/production)
 - hotfix
 - release-candidate
 - beta
 - dev
 - feature

The only branch guaranteed to exist at any point in time is master, and beta and dev will typically exist. All other branches/branch types will be created as needed. The workflow is the following:

  1. Branch off of `dev` to create a new branch called `feature/<task name>`.
  2. Build the feature.
  3. Create a pull request for merging into dev.
  4. Request a review from another member and make any following corrections. Also ensure that all CI tests pass too.
  5. Bug the scrum master to merge the branch into `dev`.

From this point on, the scrum master will do the following:

  1. Merge the new branch into `dev`. Request a rebase from the branch creator if necessary.
  2. Once ready, merge `dev` into beta.
  5. If any requests are made, make changes to release candidate and update `beta`.
  3. Once ready, merge `beta` into a release candidate branch.
  4. Repair any found bugs.
  6. If everything is satisfactory, merge the release candidate branch into master and create a new release.

If needed, the workflow may be revised.

The purpose of the beta branch is to allow our client to see any new features in a public build and make any requests based on what she sees.

Hotfix branches will be created as bugs are discovered in production.

We will use PivotalTracker's GitHub integration to link tickets with commits. Additionally, GitHub notifications will be enabled in our Slack.

Automated deployment will be implemented for `dev`, `beta`, and `master` (production).
