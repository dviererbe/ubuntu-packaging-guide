.. _use-schroots:

Use schroots
============

.. caution::

    Work in progress!

Create a Schroot
----------------

.. code:: bash

    mk-sbuild lunar

.. code::

    To CHANGE the golden image: sudo schroot -c source:lunar-amd64 -u root
    To ENTER an image snapshot: schroot -c lunar-amd64
    To BUILD within a snapshot: sbuild -A -d lunar-amd64 PACKAGE*.dsc

Listing all Schroots
--------------------

.. code:: bash

    $ schroot --list --all

Enter a running session
-----------------------

.. code:: bash

    # Args
    # -b [ --begin-session ]       Begin a session; returns a session ID
    # -c [ --chroot ] arg          Use specified chroot
    # -e [ --end-session ]         End an existing session
    # -l [ --list ]                List available chroots
    # -r [ --run-session ]         Run an existing session
    # --all-sessions               Select all active sessions
    # -n [ --session-name ] arg    Session name (defaults to an automatically 
    #                              generated name)

    # start session
    $ schroot -b -c lunar-amd64 [-n session-name]
    lunar-amd64-493f3454-ed37-423b-b5ed-26bc439c3e5e

    # or list all sessions:
    $ schroot -l --all-sessions
    session:lunar-amd64-493f3454-ed37-423b-b5ed-26bc439c3e5e

    # enter session
    $ schroot -r -c lunar-amd64-493f3454-ed37-423b-b5ed-26bc439c3e5e

    # end session
    $ schroot -e -c session:lunar-amd64-493f3454-ed37-423b-b5ed-26bc439c3e5e

Deleting a Schroot
------------------

1. Remove the stanza for the chroot
    .. code:: bash
    
        sudo rm /etc/schroot/chroot.d/sbuild-lunar-amd64

#. Remove the chroot from the disk
    .. code:: bash

        sudo rm -rf /var/lib/schroot/chroots/lunar-amd64

    .. include:: ./test.sh
        :code: bash
        :start-after: # Start A
        :end-before: # End A

Further reading
---------------

- `SimpleSbuild -- Ubuntu Wiki <SimpleSbuildUbuntuWikiEntry_>`_
- `schroot(1) -- man page <SchrootManPage_>`_

.. _SimpleSbuildUbuntuWikiEntry: https://wiki.ubuntu.com/SimpleSbuild
.. _SchrootManPage: https://manpages.ubuntu.com/manpages/lunar/en/man1/schroot.1.html