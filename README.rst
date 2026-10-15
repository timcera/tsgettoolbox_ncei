.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_ncei
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_ncei?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_ncei
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_ncei/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_ncei
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_ncei/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_ncei
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_ncei/
    :height: 20

tsgettoolbox_ncei - Quick Guide
===============================
The 'tsgettoolbox_ncei' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
California Data Exchange Center (CDEC).  The tsgettoolbox_ncei will work with
Python and 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox NCEI API`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_ncei

    OR

    $ conda install -c conda-forge tsgettoolbox_ncei

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'ncei', type 'tsgettoolbox
ncei --help'.

+-----------------+---------+--------+---------+----------+-----------------------+
| Sub-command     | Spatial | Time   | Type    | Time     | Description           |
|                 | Extent  | Extent |         | Interval |                       |
+=================+=========+========+=========+==========+=======================+
| ncei_ghcnd_ftp  | global  | varies | station | D        | NCEI Global           |
|                 |         |        |         |          | Historical            |
|                 |         |        |         |          | Climatology Network - |
|                 |         |        |         |          | Daily (GHCND) from    |
|                 |         |        |         |          | FTP server.           |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_ghcnd      | global  | varies | station | D        | NCEI Global           |
|                 |         |        |         |          | Historical            |
|                 |         |        |         |          | Climatology Network - |
|                 |         |        |         |          | Daily (GHCND) from    |
|                 |         |        |         |          | web services.         |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_gsod       | global  | varies | station | D        | NCEI Global Summary   |
|                 |         |        |         |          | of the Day (GSOD)     |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_gsom       | global  | varies | station | M        | NCEI Global Summary   |
|                 |         |        |         |          | of the Month (GSOM)   |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_gsoy       | global  | varies | station | A        | NCEI Global Summary   |
|                 |         |        |         |          | of Year               |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_normal_ann | global  | varies | station | A        | NCEI annual normals   |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_normal_dly | global  | varies | station | D        | NCEI daily normals    |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_normal_hly | global  | varies | station | H        | NCEI hourly normals   |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_normal_mly | global  | varies | station | M        | NCEI monthly normals  |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_precip_15  | global  | varies | station | 15T      | NCEI 15 minute        |
|                 |         |        |         |          | precipitation         |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_precip_hly | global  | varies | station | H        | NCEI hourly           |
|                 |         |        |         |          | precipitation         |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_annual     | global  | varies | station | A        | NCEI annual data      |
|                 |         |        |         |          | summaries             |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_ghcndms    | global  | varies | station | M        | NCEI GHCND Monthly    |
|                 |         |        |         |          | Summaries (GHCNDMS)   |
+-----------------+---------+--------+---------+----------+-----------------------+
| ncei_ish        | global  | varies | station | H        | NCEI Integrated       |
|                 |         |        |         |          | Surface hourly        |
+-----------------+---------+--------+---------+----------+-----------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| T                 | Minute      |
+-------------------+-------------+
| H                 | Hourly      |
+-------------------+-------------+
| D                 | Daily       |
+-------------------+-------------+
| M                 | Monthly     |
+-------------------+-------------+
| A                 | Annual      |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    start_date = "2010-01-01"
    end_date = "2013-01-01"
    df = tsgettoolbox.ncei_precip_hly(
        "COOP:087440",
        start_date=start_date,
        end_date=end_date,
    )
    print(df.head())

Refer to the API Documentation at `tsgettoolbox NCEI API`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox ncei_precip_hly \
        "COOP:087440" \
        --start_date="2010-01-01" \
        --end_date="2013-01-01" > output.csv

Refer to the command line documentation at `tsgettoolbox NCEI CLI`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_ncei/overview.
https://github.com/timcera/tsgettoolbox_ncei

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/index.html
.. _tsgettoolbox NCEI API: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/_function_autosummary/tsgettoolbox.ncei_annual.html
.. _tsgettoolbox NCEI CLI: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html#ncei-annual
