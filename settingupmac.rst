Setting up a Mac
----------------

- Homebrew > all (except maybe Vagrant)
- Lion includes Postgres


.. code-block:: bash

    brew install postgres

    launchctl load ~/Library/LaunchAgents/<something>/postgres.plist
    # or unload

    # config in /usr/local/var

- OS X uses clang by default. Some Python packages hate that.

.. code-block:: bash

    CFLAGS = ... march-nocona ...

    CC = /usr/bin/gcc


.. code-block:: bash

    /etc/paths

