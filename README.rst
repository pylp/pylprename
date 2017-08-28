==========
PylpRename
==========


Information
===========

**pylprename** is a plugin for `Pylp`_ that rename files in a stream.


Installation
============

Install **pylprename** with ``pip``::

    pip install pylprename

If you don't have Python ``Scripts`` folder in your PATH, you can run also::

    python -m pip install pylprename


Usage
=====

The usual use of **pylprename** is as follows:

.. code:: python

    import pylp
    from pylprename import rename

    pylp.task('default', lambda:
        pylp.src('file.py')
        # .pipe(a_plugin())        
          .pipe(rename('new-name.py'))
          .pipe(pylp.dest('build'))
    )


.. _Pylp: https://github.com/pylp/pylp