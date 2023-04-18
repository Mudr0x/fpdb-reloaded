About this fork
===============

This is a revival of the original FPDB project from SourceForge: https://sourceforge.net/projects/fpdb/
It comes with my personal reworking, fixes and improvements.

Why?
----

This fork aim is to maintain continuous working update of the abandoned original FPDB project version based upon GTK, best suited for Windows/linux as an alternative to actual FPDB Qt version port from fpdb-chaz repo: https://github.com/ChazDazzle/fpdb-chaz, best suited for MacOs which remains the only one still maintained by now, but only working under Python 2.7 x64bit version.
But be happy! :smile:
I also maintain on both FPDB GTK (here) and Qt version same reworks, fixes and improvements on my fork of fpdb-chaz repo here: https://github.com/Mudr0x/fpdb-chaz/tree/Mudr0x  for FPDB Qt version.

Anyway on MacOs, a python GTK application is not required to pass through X-Window server to run.
You can simply run it with: `xvfb-run ./runMyApp`
(You will find the xvfb-run utility in the xvfb package.)

*So this fork is also perfectly suitable for Mac users.* :wink:

How?
----

To run from source under Python 2.7 32bit (x86) version follow the following walkthrough: https://github.com/Mudr0x/fpdb-reloaded/blob/Mudr0x/packaging/windows/py2exeWalkthroughPython27.txt

For Python 2.7  x64bit version install the following in sequence (accept all default options) there should be no errors !

- **Python 2.7** ... install from https://www.python.org/ftp/python/2.7.18/python-2.7.18.amd64.msi with Add Python to environment PATH option

- **matplotlib** ... needed version is 1.1.0 you can install via `pip install matplotlib==1.1.0` or download install package from https://sourceforge.net/projects/matplotlib/files/matplotlib/matplotlib-1.1.0/matplotlib-1.1.0.win-amd64-py2.7.exe

- **pywin32** ... https://sourceforge.net/projects/pywin32/files/pywin32/Build216/pywin32-216.win-amd64-py2.7.exe

- **pokereval** ... `pip install pokereval`

- **cdecimal** ... install via pip unofficial package cdecimal-2.3-cp27-cp27m-win_amd64.whl from https://www.lfd.uci.edu/~gohlke/pythonlibs/#cdecimal

- **winpaths** ... `pip install winpaths`

- **python PIL** ... https://github.com/lightkeeper/lswindows-lib/blob/master/amd64/python/PIL-1.1.7.win-amd64-py2.7.exe?raw=true

- **pygtk and gtk2 runtime** ... use my GTK2 runtime version (GTK-2.22.1-runtime.zip) from https://github.com/Mudr0x/fpdb-chaz/tree/Mudr0x/packaging/windows and add its bin folder (e.g. C:\GTK\bin) to environment PATH, and install unofficial PyGTK modules for Py2.7x64 from: https://www.lfd.uci.edu/~gohlke/pythonlibs/#pygtk

- **get the fpdb sourcecode** ... git clone https://github.com/Mudr0x/fpdb-reloaded.git

- **beautifulsoup4** ... `pip install bs4`. In addtiion you have to replace on code all occurrences of `import BeautifulSoup` by `import bs4`

- **xlrd** ... `pip install xlrd`

- **numpy** ... `pip install numpy`

- **GTK fonts** ... additionally you can install them to avoid warnings from: https://github.com/Mudr0x/fpdb-reloaded/packaging/windows/fonts.zip

- **Optional database installation**:

************************************************************
***Most people can STOP NOW, This step is only needed if you do not want to use the standard database, or if you are a developer wanting to build an executable package !!!!***
*************************************************************

- For mysql support, or if you are a exe developer, do this

*** Note that this driver package supports mysql version 5.1.34-win32 and python 2.7 only ***

download and install.....
mysql-python 1.2.3 ... http://sourceforge.net/projects/mysqlpythonwinx64py272/files/MySQL-python-1.2.3.win-amd64-py2.7_2.exe

- For postgres support, or if you are a exe developer, just run: `pip install psycopg2`



- **Test python and your fpdb installation from sourcecode**

Open the python command line and make sure everything imports.

import gtk
import win32gui
import numpy
import matplotlib
import winpaths

- **Basic FPDB testing**:

Navigate to your fpdb dir and run: `python run_fpdb.py`


If you want all-in EV calculation, you'll also want pokereval and
in addition install my already pypokereval compiled package for Py2.7x64 (pypoker-eval-x64 folder) from: https://github.com/Mudr0x/fpdb-reloaded/packaging/windows/pypoker-eval-x64

Distributions
------------------

Again again be happy! :smile:
I also provide on my Releases an already FPDB compiled distribution and a Windows Installer made with the free powerful InstallForge: https://installforge.net/download/ ... For lazy people :stuck_out_tongue:

Reworking, fixes and improvements
------------------

- Rebase of the project into one main folder, adandoning pyfpdb folder which can cause ugly bugs when packaging especially under Windows
- Fix of importing issue on some poker sites
- Fix of graph tourney viewer with other currencies than dollars
- Fix of log viewer
- Fix of minor bugs

Please report any problems using the
[github issue tracker](https://github.com/Mudr0x/fpdb-reloaded/issues).
