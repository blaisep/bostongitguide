:auto-console: true
:css: ./css/boston.css
:data-transition-duration: 2000
:skip-help: true

.. title:: Find your way through git (aka how to think about git)

About this talk
===============

Why these Goals ?
-----------------

    - This talk provides a way to reason about git in terms of your activity and needs.
    - We use the metaphor of characters to make it playful and make it stick. We hope that after this talk, these metaphors and terms will make more sense.

    - Clients as dialects, (the CLI, plugins, the gui, the API)
    - Hosts as states, (Local: the `.git` folder, Github, Gitlab)
    - Branches as tour routes... (Stage, Commits, Tags, Branches, Origin)
    - Activities as characters (readers, writers, admins)

We don't expect these terms to make sense now. They serve as a baseline and we will review them at the end.

----

About this talk
===============

Why not these Goals ?
---------------------

    - Plenty of materials cover git in general
    - True skills benefit from practice, this talk is meant to help you find what you're looking for


----

About the use of personas
=========================

Personas as characters
----------------------

    - The tourist
    - The merchant
    - The diplomat
    - The explorer

----

About the use of personas
=========================

Why use characters ?
--------------------

Git has lots of moving parts. Most resources present one path with all of the pieces eventually on display.
The purpose of the characters is to help remember the key aspects of how you use git.

Each character has a mission, resources and unlocks achievements

----

What kind of traveler are you?
==============================

Missions
---------

    - Are you sightseeing? (download, ``clone``, ``pull``)
    - Traveling for business? (push, merge, rebase)
    - Representing your government? (``remote set-url``, ``upstream``)
    - Scientific research?

----

What kind of traveler are you?
==============================

Resources
---------

    - credentials: a user login, ssh keys,
    - local repository
    - remote repository
    - commits
    - branches
    - clients: CLI, GUI, API

----

Pro -Tip
========

It's best to learn with the CLI, then use GUIs and APIs judiciously


What kind of traveler are you?
==============================

Achievements
------------

    - Pull commits from origin
    - Push commits to origin
    - Merge/rebase changes
    - Use multiple github accounts
    - Use multiple remotes

----

The Tourist
===========

Mission
-------

Tourists visit places, sometimes they need a visa. Bring back code to put in your local repository.
With no expectation to return. Only the local repo matters and you rarely visit the server.

----

The Tourist
===========

Resources
`````````
    - Optional: a user account
    - Use a GUI client if you like, or the CLI if you plan to visit often.

----

The Tourist
===========

Achievement
-----------

    - Download the zip for just the files,
    - Use https to conserve the git structure.
    - git ``commit`` to record changes

----

The Tourist
===========

Achievement
-----------

Three ways a tourist can take a snapshot:
    - https://github.com/blaisep/bostongitguide/archive/refs/heads/main.zip
    - https://github.com/blaisep/bostongitguide.git
    - git@github.com:blaisep/bostongitguide.git

.. note::
    Break down the URLs into protocol, org, repo, content type

The Tourist
===========

Achievement
-----------

    - Make a change
    - Add the change
    - Commit the change
    - ``git log`` to view the change


----

The Diplomat
============

When you need to push changes from your local repo or you need to make changes on the server, you are no longer a tourist.

.. note::
    Diplomats need a special passport and credentials: ssh (public and private key)
    They get access to restricted places. As frequent travelers, they will use the CLI
    *Special Achievement:* use multiple accounts on the same service (eg. Github.work, Github.home)


Mission
-------

    - push commits to origin
    - merge changes
    - rebase (squash)

----

The Diplomat
============

Resources
---------
    - Your ssh credentials
    - Your ssh config file
    - Access privileges (on the server) to push upstream

----

The Diplomat
============

Achievement
-----------

    - push changes upstream

----

The Diplomat
============

Unlock Achievement
-------------------

    0. Create your ssh key pair
    1. Add your *PUBLIC* key to Github
    2. Add your *PRIVATE* key to your ssh-agent
    3. Include the path to your *PRIVATE* key file in ``.ssh/config``

The Diplomat
============

Unlock Achievement
-------------------

.. code-block:: bash
    Host github.com
    User blaisep
    UseKeychain yes
    AddKeysToAgent yes
    IdentityFile /Users/bpabon/.ssh/id_ed25519

---

The Merchant
============


Achievement:
------------

use multiple accounts on the same service (eg. Github.work, Github.home)

What to pack



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