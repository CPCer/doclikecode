====================
ReST Quick Reference
====================

Underline titles with punctuation
=================================

.. _rst_example:

ReST example markup
-------------------

|替代图片|

.. |替代图片| image:: https://imgsa.baidu.com/%C1%AD%B5%B6%CA%D5%B8%EE%BB%FA%BC%D7/pic/item/b7f3f57c92d6145b29388a11.jpg

*Italic*\ **bold** ``name`` ``function()`` ``expression = 3 + 3``
(`Hyperlink <http://en.wikipedia.org/wiki/Hyperlink>`_) `Link`_

.. _Link: http://en.wikipedia.org/wiki/Link_(The_Legend_of_Zelda)
.. image:: images/python-logo.png
.. A comment block starts with two periods, can continue indented.

A paragraph is one or more lines of un-indented text, separated
from the material above and below by blank lines.

     “Block quotes look like paragraphs, but are indented with
     one or more spaces.”

| Because of the pipe characters, this will become one line,
| And this will become another line, like in poetry.

term
   Definition for the “term”, indented beneath it.
another term
   And its definition; any of these definitions can continue on for
   several lines by — you guessed it! — being similarly indented.

* Each item in a list starts with an asterisk (or “1.”, “a.”, etc).
* List items can go on for several lines as long as you remember to
   keep the rest of the list item indented.

Code blocks are introduced by a double-colon and are indented::

     $ mkdir docs

Examples using Sphinx markup
----------------------------

A python code block using Sphinx markup:

.. code-block:: python

     import docutils
     print help(docutils)

.. note:: This is a note using Sphinx markup.

This is a reference to :ref:`rst_example`.
