:auto-console: true
:css: ./css/boston.css
:data-transition-duration: 2000
:skip-help: true

.. title:: Find your way through git (aka how to think about git)


Why these Goals ?
-----------------

    - This talk provides a way to reason about git in terms of your activity and needs.
    - We use the metaphor of characters to make it playful and make it stick.

We hope that after this talk, these metaphors and terms will make more sense.

    - Clients as dialects, (the CLI, plugins, the gui, the API)
    - Hosts as states, (Local: the `.git` folder, Github, Gitlab)
    - Branches as tour routes... (Stage, Commits, Tags, Branches, Origin)
    - Activities as characters (readers, writers, admins)

We don't expect these terms to make sense now. They serve as a baseline and we will review them at the end.

----

Why not these Goals ?
---------------------

    - Plenty of materials cover git in general
    - True skills benefit from practice, this talk is meant to help you find what you're looking for




----

Why use characters ?
--------------------

Git has lots of moving parts. Most resources present one path with all of the pieces eventually on display.
The purpose of the characters is to help remember the key aspects of how you use git.

----

What kind of traveler are you?
==============================

The Tourist (download, pull)
----------------------------

Tourists don't need a Visa. They pull code from git for local, personal consumption
With no expectation to return. Only the local repo matters and you rarely visit the server.


What to pack
    - Comes as you are, Download and https with no account required.
    - Use a GUI client if you like, or the CLI if you

Places to visit
    - Download the zip for just the files,
    - Use https to conserve the git structure.
    - git ``commit`` to record changes

----

Three ways a tourist can take a snapshot:
    - https://github.com/blaisep/bostongitguide/archive/refs/heads/main.zip
    - https://github.com/blaisep/bostongitguide.git
    - git@github.com:blaisep/bostongitguide.git

.. note::
    Break down the URLs into protocol, org, repo, content type

----

The Diplomat (commit, push)
---------------------------

Diplomats need a special passport and credentials: ssh (public and private key)
They get access to restricted places. As frequent travelers, they will use the CLI
*Special Achievement:* use multiple accounts on the same service (eg. Github.work, Github.home)

.. note::
    When you need to push changes from your local repo or you need to make changes on the server, you are no longer a tourist.

What to pack
    - Your ssh credentials (Light or Heavy)
    - Your ssh config
    - Access privileges (on the server) to push upstream


Places to visit
    - Push
    - Pull Request (Github)
    - Merge Request (Gitlab)

----

The Merchant (Branch vs Tag, Merge vs Rebase)
---------------------------------------------

Merchants travel around trading and adding value along the way.
*Special Achievement:* Multiple remotes (servers)

What to pack
    - Access privileges,
    - hooks (pre-commit)
    - CI/CD Workflows

Places to visit
    - remotes
    - Tags vs Branches
    - Rebase vs Merge
    - Merge conflicts

----


The Explorer
------------

Explorers discover a create descriptions of the unknown for the benefit of others.

(init, local, remote, mirrors, upstream, downstream)
The `.git` folder, Local, Remotes, Origin
*Special Achievement:* add an upstream remote

Things to pack
    - Access privileges

Places to visit
    - Git log
    - init, mirror
    - remote add

----

Questions
---------