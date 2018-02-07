scapy
=====

* This repository contains list of steps to get scapy running on Windows with Python 2.7.
* All credits, rights, and thanks go to the respective application and code developers.
* Please see [scapy documentation](http://www.secdev.org/projects/scapy/doc/installation.html#windows) for reference on installation, dependencies, and usage.
* Please see each install, application, library, etc., for license agreements, and make sure you comply.

# Pre-requisites
These steps were tested on Windows 8.1 64-bit.
Currently using Visual Studio to compile some of the dependencies (may look for free alternatives later).
Visual Studio could be skipped if installing only pre-compiled binaries.

You should have the following installed already:

Package  | Comments  |
---------|-----------|
[Python 2.7](https://www.python.org/downloads/) | Tested with 32-bit version
Visual Studio - use [Microsoft Visual C++ Compiler for Python 2.7](https://www.microsoft.com/en-us/download/details.aspx?id=44266) OR get a [licensed version](http://msdn.microsoft.com/en-us/vstudio/aa718325.aspx) | Tested with VisualStudio 2013
[pip](https://pypi.python.org/pypi/pip/) or [setuptools](https://pypi.python.org/pypi/setuptools) | You should consider using [virtualenv](https://pypi.python.org/pypi/virtualenv)
[7zip](http://7-zip.org/download.html) | Or a similar zip/tar.gz extraction utility
[chocolatey](http://chocolatey.org/) | Recommended for easy installation of dependencies

Note that you will have to run most/all of the installs from elevated privileges ('run as administrator').

# Install Applications
Pick the add-ons you are planning to use.

**Minimum requirement is npcap.**

Application  |   Chocolatery   |
-------------|-----------------|
[npcap](https://nmap.org/npcap/)  |  `\`  |
[cryptography](https://github.com/pyca/cryptography) | `\` |
[Graphviz](http://graphviz.org/Download_windows.php) |  `choco install Graphviz`  |
[Matplotlib](https://matplotlib.org/)  |  `choco install matplotlib` |
[imagemagick](http://www.imagemagick.org/script/binary-releases.php#windows)  | `choco install imagemagick.app`  |
[miktex](http://miktex.org/download)  | `choco install miktex`  |
[wireshark](https://www.wireshark.org/download.html)  |  `choco install wireshark`  |
[nmap](http://nmap.org/download.html)  |  `choco install nmap`  |
[vpython](http://www.vpython.org/contents/download_windows.html) |  |
[queso](http://www.packetstormsecurity.org/UNIX/scanners/queso-980922.tar.gz)  |  |
[tortoisehg](http://tortoisehg.bitbucket.org/download/index.html)  |  `choco install tortoisehg` |

- You can replace tortoisehg with command line version of hg, or later download scapy source as a zip file.
- MikTex (and others) have to be installed to a path without space characters.
- Add to the PATH any other application you installed. For example, for MikTex - add the (MikTek Install Dir)\miktex\bin subdirectory to your PATH.

# Install Scapy Dependencies
Pick the add-ons you are planning to use. You will need at least: pyreadline, pcapy, and dnet.

From command line (pip / easy_install executables are usually under c:\python27\scripts):
- `pip install ipython`    (recommanded)
- `pip install cryptography`
- `pip install matplotlib`
- `pip install pyx==0.12.1`

Note: pyx version 0.13 and above are for Python3. As of this writing, 0.12.1 is the latest for Python2.

- Install pcapy from [link1](https://code.google.com/p/pypcap/issues/detail?id=36) or [link2](http://breakingcode.wordpress.com/2012/07/16/quickpost-updated-impacketpcapy-installers-for-python-2-5-2-6-2-7/).
- Install dnet from [link3](http://dirk-loss.de/scapy/dnet-1.12.win32-py2.7.exe) or [link4](https://twitter.com/dloss/status/18457222544).

# Install Scapy
- Get latest scapy source code from [source](https://github.com/secdev/scapy), or [as a zip file](https://github.com/secdev/scapy/archive/master.zip).
- Open command prompt in the source folder and run: `python setup.py install`

- Unzip queso (downloaded above) to your Scapy directory (C:\Python27\Lib\site-packages\scapy).


# Test & Run
- Run `scapy.bat` from (c:\python27\scripts).
- If start up complains about missing dependencies - install them.
- If you see an error about mismatch between pcap and dnet:
  - Try closing other sniffers and restart scapy.
  - Try re-installing winpcap and restart.
  - If still not working, have a look at [1](http://article.gmane.org/gmane.comp.security.scapy.general/3932), [2](http://article.gmane.org/gmane.comp.security.scapy.general/3937), [3](http://article.gmane.org/gmane.comp.security.scapy.general/3902).

# Links
- [Scapy home page](http://www.secdev.org/projects/scapy/).
- [Scapy docs](http://www.secdev.org/projects/scapy/doc/index.html).
- [Scapy demo](http://www.secdev.org/projects/scapy/demo.html).
- The Very Unofficial [Dummies Guide to Scapy](http://scapy-guide.googlecode.com/files/ScapyGuide.pdf).

# Final Words
- Please leave a ticket if the above steps need to be update.
- Please add a comment in the [wiki](https://github.com/zlorb/scapy/wiki) on working configurations and additional tips on how to get there.
