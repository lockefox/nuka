.. Do not edit this file. It is generated. See docs/utils.py

==================================================================
:mod:`nuka.tasks.apt`
==================================================================

.. automodule:: nuka.tasks.apt


nuka.tasks.apt.debconf_set_selections
==================================================================

.. autofunction:: debconf_set_selections


Example:

.. code-block:: python

    res = await apt.debconf_set_selections(
        [('adduser', 'adduser/homedir-permission', 'true')]
    )
    assert bool(res)



nuka.tasks.apt.install
==================================================================

.. autofunction:: install


Example:

.. code-block:: python

    res = await apt.install(['python'])
    assert bool(res)



nuka.tasks.apt.source
==================================================================

.. autofunction:: source


Example:

.. code-block:: python

    if 'wheezie' in host.hostname:
        n = 'wheezie'
    elif 'jessie' in host.hostname:
        n = 'jessie'
    else:
        n = 'stretch'
    src = 'deb http://apt.dockerproject.org/repo/ debian-{0} main'.format(n)
    res = await apt.source(
        name='docker',
        key='https://yum.dockerproject.org/gpg',
        src=src,
    )
    assert bool(res)
    src = 'deb http://deb.bearstech.com/debian {0}-bearstech main'.format(n)
    res = await apt.source(
        name='bearstech',
        key='https://deb.bearstech.com/bearstech-archive.gpg',
        src=src,
    )
    assert bool(res)



nuka.tasks.apt.update
==================================================================

.. autofunction:: update


Example:

.. code-block:: python

    res = await apt.update(cache=3600)
    assert bool(res)



