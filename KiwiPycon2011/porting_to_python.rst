==========================================
Porting (and staying ported) to Python 3
==========================================

by Leon Matthews

.. note:: presenter had slides with gradient background so things were hard to read. Sigh.

Overview
========

 * Why bother?
 * Possible strategies 
 * Porting to Python 3
 * Maintaining Python 2 **AND** Python 3

    * Two concurrent code bases (Python 2 AND Python 3) 
    * IF/ELSE logic for imports/code

Why Bother?
============

 * Python 3 is the future of Python
 * Industry leading unicode support
 * It's nicer - Python 2 after wart removal
 * Other people may be waiting on you
 
Sample
=========

.. sourcecode:: python

    # python 2
    print 1, 2

    # python 3
    print(2, 3)
    print(2, 3, file=sys.stderr)    

Porting to Python 3
====================

Already there if:

* You can run under Python 2.7
* You have handle on Unicode

Lots of issues
===============

* Syntax renames

    * urllib2 to urllib
    * print to print()
    
* Changed behavior

    * Sorting comparisons are different
    * division
    
* unicode

    * All strings in Python 3 are Unicode
    * Initial transition can hurt but then it gets easy
    
.. sourcecode:: python

    import io
    io.open(path, 'rt',encoding='utf-8')
    a = u'Unicode String'
    b = b'Binary string'

You now have a working port, now what?
=======================================

* Two code bases
* Maintain both
* Leave one to die in the cold?
* Way too common a situation
    
