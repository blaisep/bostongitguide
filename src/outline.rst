:auto-console: true
:title: Find your way through git (aka how to think about git)
:author: Blaise Pabon
:description: A guide to finding your way around git.
:keywords: presentation, restructuredtext, impress.js, git
:css: ./css/boston.css


Finding your way around ``git``
===============================

About this talk
-----------------

    - This talk provides a way to reason about git in terms of your requirements and needs.
    - We use scenarios similar to role playing games to make it playful and make it stick. We hope that after this talk, these metaphors and terms will make more sense.
    - Each scenario will include a persona, mission, some resources, and unlocking an achievement.

----

About this talk
===============

Why not these Goals ?
---------------------


    - Plenty of materials cover git in general
    - Most materials explain how git works
    -


----

About Personas
==============

Personas as characters
----------------------

    - The tourist: visits, returns home with souvenirs
    - The merchant: exchanges goods with other merchants
    - The diplomat: multiple passports, moves across boundaries
    - The explorer: Creates new outposts, returns with observations

----

About Personas
==============

Why use characters ?
--------------------

Git has lots of moving parts. Most resources present one path with all of the pieces eventually on display.
The purpose of the characters is to help remember the key aspects of how you use git.

Each character has a
    - mission: (eg. clone a remote repo and push local commits)
    - resources: (eg. github account, local repo, ssh config)
    - unlock achievement: (eg. config ssh client)

----

Choose your character
=====================

Missions
---------

    - The Tourist: Are you sightseeing? (download, ``clone``, ``pull``)
    - The Merchant: Traveling for business? (push, merge, rebase)
    - The Diplomat: Representing your government? (``remote set-url``, ``upstream``)
    - The Explorer: Scientific research?

----

Choose a character
==================

Resources
---------

    - credentials: a user login, ssh keys,
    - local repository
    - remote repository
    - commits
    - branches
    - clients: CLI, GUI, API

----

About resources
===============

We will discuss git generally, but it's worth noting that it comes in many flavors.

Repo
----

    - A local repo is a directory with a sub-directory called `.git`
    - The local repo contains a copy of the whole project
    - Only you can access your local repo.
    - If you want to share code with others, you'll need a remote copy on a server.

The local repo
--------------

Your local `.git` directory will look like this:

.. code-block::

    ├── HEAD
    ├── config
    ├── description
    ├── hooks
    │   ├── commit-msg.sample
    │   ├── pre-commit.sample
    │   ├── pre-push.sample
    │   └── update.sample
    ├── info
    │   └── exclude
    ├── objects
    │   ├── info
    │   └── pack
    └── refs
        ├── heads
        └── tags

Good. That's the last time you should ever see those directories.

Clients
-------

There are many, many options. They can be divided into CLI, GUI and API.
It's best to learn with the CLI, (because the command structure closely follows the structure of git and because it it universal.
Later, you can use GUIs and APIs judiciously.

Servers
-------

There are also many options:
    - GitLab,
    - Gitea,
    - BitBucket,
    - GitHub Enterprise, etc.

Choose a character
==================

Unlock achievements
--------------------

    - Pull commits from origin
    - Push commits to origin
    - Merge/rebase changes
    - Use multiple github accounts on the same device
    - Use multiple remotes: upstream, downstream

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
---------

    - a Github user account
    - Use a GUI client if you like, or the CLI if you plan to visit often.

----

The Tourist
===========

Achievement
-----------

    - Download the zip for just the files,
    - Use https to conserve the git structure.
    - Configure `ssh` and clone your repo using ssh

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

    - Create your SSH key, copy the pubkey to github, clone your repo using ssh.

    0. Create your ssh key pair
    1. Add your *PUBLIC* key to Github
    2. Add your *PRIVATE* key to your ssh-agent
    3. Include the path to your *PRIVATE* key file in ``.ssh/config``

Achievement: ssh config
-----------------------

A tourist's config looks like this:

.. code-block:: bash

    Host github.com
    User blaisep
    UseKeychain yes
    AddKeysToAgent yes
    IdentityFile /Users/bpabon/.ssh/id_ed25519

Later, you will see how Diplomats extend those settings.

Achievement: git config
-----------------------

Configure your git settings. Do NOT edit the config files in ``.git``, using the ``git config...`` commands instead.
    - Set your user name and email

Achievement (optional)
----------------------

    - Make a change
    - Add the change
    - Commit the change
    - ``git log`` to view the change
    - push to origin


----

The Diplomat
============

When you need to push changes from your local repo or you need to make changes on the server, you are no longer a tourist.

.. note::
    Diplomats need a special passport and credentials: ssh (public and private key)
    They get access to restricted places. As frequent travelers, they will use the CLI
    *Special Achievement:* use multiple accounts for the same service (eg. Github.work, Github.home)


Mission
-------

Missing...

---

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

Mission
-----------

    - Multiple accounts on the same device (eg. personal and professional)
    - use multiple accounts on the same service (eg. Github.work, Github.home)

----

The Diplomat
============

Unlock Achievement
-------------------



The Diplomat
============

Unlock Achievement
-------------------


---

The Merchant
============

Merchants travel around trading and adding value along the way.


Mission
-------

    - follow the branching strategy (``merge`` , ``rebase``, ``git --amend`` )
    - push commits to origin
    - merge changes
    - rebase (squash)

---

The Merchant
============

Resources
---------

    - A keypair for each account, both on the same laptop
    - ``push`` privileges to both remotes

---

The Merchant
============

Achievement:
------------

    - Push changes to a personal repo
    - Push changes to a work repo

----

The Merchant
============

Achievement:
------------

This achievement requires three steps:

    0. A keypair for each account
    1. Edits to your ``~/.ssh/config``
    2. Adjust the name and email of your repos
    3. ``git remote orgin set-url`` of your personal remote

---

The Merchant
============

.. code-block:: bash

    Host github.com-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/github-personal_ed25519

---

The Merchant
============

The ssh config
--------------

.. note::
    Places to visit
        - remotes
        - Tags vs Branches
        - Rebase vs Merge
        - Merge conflicts

----

The Merchant
============

The remote URL
--------------

.. code-block::

    git remote origin set-url git@github.com-personal:blaisep/bostongitguide.git

----

The Explorer
============

Explorers discover a create descriptions of the unknown for the benefit of others.

---


Achievement
------------

Fancy commit history with ``git log``

Simple: ``git log --color --graph --all --pretty=lt``
Deluxe:

.. code-block::

    git config --global alias.lg "log --color --graph \
    --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' \
    --abbrev-commit"

And then, totally over-the-top:
https://github.com/alfunx/.dotfiles/blob/master/.gitconfig#L218-L224

----

Questions
=========

...about the material

----

Requests
========

...for improvements