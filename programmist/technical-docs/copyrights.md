# Copyright Regulations

This doc describes when and where to add your name in the copyrights of a module. 
It depends on type of the update you made. Such types can be specified by how version is changed.
Version change is changing of of the three numbers _x.y.z notation_.
Check here more information: [\_\_manifest\_\_.py](__manifest__.md#version)

## \_\_manifest\_\_.py file

### "author" attribute

Only for author of init version or updates for type  __X__, for example add your name here when you change version from __1__.0.0 to __2__.0.0 

### Comments at the beginning of file

You are free to add your name on any update, even on fixing grammar, indent, missed space or comma, line break at the end of file, lints, etc.

## README file

Put your name here, if you made a change of type __Y__ (or __X__). Or if you made [migration scripts](https://odoo-development.readthedocs.io/en/latest/maintenance/data-migration.html)

Use following format:

    Contributors
    ------------

    * `Dinar Gabbasov <https://it-projects.info/team/GabbasovDinar>`__:
        * :one::zero: init version of the module
        * :one::zero: New feature: ...
    * `Kolushov Alexandr <https://it-projects.info/team/KolushovAlexandr>`__
        * :one::one: Port
    * `Ivan Yelizariev <https://it-projects.info/team/yelizariv>`__
        * :one::one: Migration script

## Files

For regular code files (``*.py``, ``*.xml``, ``*.js``, etc) add your copyright line 
if you made update change in that file and type of update is __Z__ (or __Y__, or __X__).
