# GitHub Issue Migration

This is a dumb little script that migrates issues from one GitHub repo to another.

- Issue titles are copied unmodified.
- Issue body links to original, and attributes to original author, like so:

> @username opened old-org/old-repo#X
> 
> original issue body

- Comments are copied and attributed to the original author:

> @username \[commented\](link-to-original)
> 
> original comment

- The original issue is closed, with a comment linking to the new issue:

> Issue moved to new-org/new-repo#X

- labels, milestones, and assignee are also copied, since that's what we want in IPython/Jupyter.
  If labels and/or milestones are missing on the target repo, they will be created.

## Install:

    gem install octokit highline netrc

Tf you have a `~/.netrc` file, check that the permission are `0600`. 

## Usage

There's not much to it. Just specify a source and target repo, then one or more issue numbers:

    migrate-issues org/from-repo other-org/to-repo 1 2 3 4 ...

