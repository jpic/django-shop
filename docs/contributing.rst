.. _contributing:

=============
Contributing
=============

Naming conventions
==================

The official name of this project is **djangoSHOP**. Third party plugins for **djangoSHOP** shall
follow the same naming convention as for plugins of **djangoCMS**: Third party package names shall
start with **djangoshop** followed by a dash; no space shall be added between **django** and
**shop**.

**DjangoSHOP** should be capitalised at the start of sentences and in title-case headings.

When referring to the package, repositories and any other things in which spaces are not permitted,
use **django-shop**.


Running tests
==============

It's important to run tests before committing :)


Setting up the environment
--------------------------

We highly suggest you run the tests suite in a clean environment, using a tool such as
`virtualenv <http://pypi.python.org/pypi/virtualenv>`_.

1. Clone the repository and cd into it:

.. code-block:: shell

	git clone https://github.com/awesto/django-shop
	cd django-shop

2. Create a virtualenv, and activate it:

.. code-block:: shell

	virtualenv ~/.virtualenvs/django-shop
	source ~/.virtualenvs/django-shop/bin/activate

3. Install the project in development mode:

.. code-block:: shell

	pip install -e .

4. Install the development requirements:

.. code-block:: shell

	pip install -r requirements/django18/testing.txt

That's it! Now, you should be able to run the tests::

	py.test tests

We use `tox <http://codespeak.net/tox/>`_ as a CI tool. To run the full CI test suite and get a
coverage report, all you have to do is this:

.. code-block:: shell


	pip install tox
	tox

If you work on a certain part of the code base and you want to run the related tests and get a
coverage report, you can do something like this:

.. code-block:: shell

	coverage run $(which py.test) tests/test_money.py && coverage report -m shop/money/*.py

.. note::

	Using tox and py.test is optional. If you prefer the conventional way of running tests, you can
	do this: ``django-admin.py test tests --settings shop.testsettings``


Community
==========

Most of the discussion around django SHOP takes place on IRC (Internet Relay Chat), on the freenode
servers in the #django-shop channel.

We also have a mailing list and a google group::

	http://groups.google.com/group/django-shop


Code guidelines
================

Unless otherwise specified, follow :pep:`8` as closely as possible.

An exception to PEP 8 is our rules on line lengths. Don’t limit lines of code to 79 characters if it
means the code looks significantly uglier or is harder to read. Consider 100 characters as a soft,
and 119 as a hard limit. Here soft limit means, that unless a line must be splitted across two
lines, it is more readable to stay with a long line.

Use the issue tracker only to report bugs. Send unsolicited pull requests only to fix bug – never
to add new features.

Use stack-overflow to ask for questions related to **djangoSHOP**.

Most pull requests will be rejected without proper unit testing.

Before adding a new feature, please write a specification using the style for
`Django Enhancement Proposals`_.

More information about how to send a Pull Request can be found on GitHub:
http://help.github.com/send-pull-requests/

.. _Django Enhancement Proposals: https://github.com/django/deps/blob/master/final/0001-dep-process.rst
