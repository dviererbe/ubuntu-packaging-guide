.. _getting-set-up:

Getting Set Up
==============

.. caution::

    Work in progress!


Create a :term:`Launchpad` Account
----------------------------------

For many common packaging tasks and to collaborate with other
:term:`Ubuntu` :term:`Contributors <Contributor>` you need a
:term:`Launchpad` ID.

1. Go to https://launchpad.net/
2. Click on the "Log in / Register" link in the top right corner
    .. image:: ../images/tutorial/getting-set-up/screenshot-of-launchpad-homepage-highlighting-register-link.png
        :width: 35 em
        :alt: Screenshot of the :term:`Launchpad` homepage with the register link highlighted

    .. note::
        You will get redirected to :term:`Ubuntu One`. This is the :term:`Ubuntu` :term:`Identity Provider`
        for :term:`Single Sign On`.

3. Create a new :term:`Ubuntu One` Account or log in in with
   an existing :term:`Ubuntu One` Account, by following the
   instructions provided.

.. _create_openpgp_key:
Create an OpenPGP key
---------------------

.. note::
    If you already have an OpenPGP key you want to use for  you can skip the remaining paragraphs of this section.

This paragraph only provides a minimal example best suited for beginners.
:manpage:`gpg(1)` and related practices can get 

Add an E-Mail Address (UID) to  an existing OpenPGP key
-------------------------------------------------------

.. note::
    If you just followed the :ref:`create_openpgp_key` section, you can scip this section.

Upload your OpenPGP key to the Ubuntu Keyserver
-----------------------------------------------


Add your OpenPGP key to Launchpad
---------------------------------


Create an SSH Key
-----------------


Add your SSH Key to Launchpad
-----------------------------


Setup Environment Variables
---------------------------

Many packaging tools look for specific 

.. code::
    export DEBFULLNAME="Your Full Name"
    export DEBEMAIL=your@email.com

Configure Git
-------------

.. code:: bash

    git config --global user.name Your Full Name
    git config --global user.email your@email.com
    git config --global commit.gpgsign true

    git config --global gitubuntu.lpuser YOUR_LAUCHPAD_USERNAME
    git config --global url."git+ssh://YOUR_LAUCHPAD_USERNAME@git.launchpad.net/".insteadof 'lp:'
    git config --global url."git+ssh://YOUR_LAUCHPAD_USERNAME@git.launchpad.net/".insteadof 'https://git.launchpad.net/'

Setup SBuild
------------

Setup LXD
---------