Introduction
============

.. image:: https://img.shields.io/pypi/v/bsedata.svg
   :target: https://pypi.org/project/bsedata/

.. image:: https://img.shields.io/pypi/l/bsedata.svg
   :target: https://pypi.org/project/bsedata/

.. image:: https://img.shields.io/pypi/pyversions/bsedata.svg
   :target: https://pypi.org/project/bsedata/

.. image:: https://img.shields.io/pypi/format/bsedata.svg
   :target: https://pypi.org/project/bsedata/

.. image:: https://readthedocs.org/projects/bsedata/badge/?version=latest
   :target: https://bsedata.readthedocs.io/en/latest/?badge=latest
   :alt: Documentation Status

bsedata is a library for collecting real-time data from Bombay Stock Exchange (India). It can be used in various types of projects which require getting live quotes for a given stock or index or build large data sets for data analysis.

.. note::

    The data provided by APIs is only as correct as provided on https://m.bseindia.com

.. warning::

    If you are facing any issue with the APIs then it may be beacuse there had been some format change recently in the way BSE reports its live quotes. Please upgrade to the latest version in order to avoid this issue. Report the issue at https://github.com/sdabhi23/bsedata/issues if it is not resolved even after upgrading the version.

Features
--------

* Getting live quotes using stock codes in Python dicttionaries
* Getting list of top losers
* Getting list of top gainers
* Getting quotes for all the indices traded in BSE
* Helper APIs to check whether a given stock code or index code is correct
* Getting list of all indices and stocks

Roadmap
-------

* Get details of an individual index
* Complete unit test coverage
* Daily OHLCV data
* Historical EOD OHLCV data

Dependencies
------------

* BeautifulSoup 4
* requests
* lxml
* A working internet connection 😉

.. warning::

    You need to have a working internet connection while using this library. It will raise ``requests.exceptions.ConnectionError`` in case there is no internet connectivity. Hence please handle this scenario in your code.

Change Log
==========

v0.4.0
------

**New Features:**

- Switched to lxml parser for better performance

**Bug Fixes:**

- Add a generic User Agent to all the requests as BSE website is blocking requests from the default requests user agent (``python-requests/2.23.0``) [:issue:`5`, :issue:`9`, :issue:`13`, :issue:`14`]

v0.3.1
------

**Bug Fixes:**

- Quick fix for getQuote method crashing due to missing ``priceBand`` attribute [:issue:`5`]

v0.3.0
------

**New Features:**

- Implement ``updateScripCodes``, ``getScripCodes`` and ``verifyScripCode`` methods to verify and search scrip codes

**Bug Fixes:**

- Fix ``getIndices`` method returning empty response
- Fix ``getQuote`` method not returning company name


v0.2.0
------

**New Features:**

- Getting quotes for all the indices traded in BSE

v0.1.0
------

**New Features:**

- Getting live quotes using stock codes
- Return data in both JSON and python (dict and list) formats
- Getting list of top losers
- Getting list of top gainers
