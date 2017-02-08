---
category: "Python"
---


When you try to install Python via pyenv and you got the error:

```
Downloading Python-2.7.11.tar.xz...
-> https://www.python.org/ftp/python/2.7.11/Python-2.7.11.tar.xz
Installing Python-2.7.11...
ERROR: The Python zlib extension was not compiled. Missing the zlib?

Please consult to the Wiki page to fix the problem.
https://github.com/yyuu/pyenv/wiki/Common-build-problems


BUILD FAILED (OS X 10.11.4 using python-build 20160602)

Inspect or clean up the working tree at /var/folders/jz/m2f2bdxj1qx9j9xnq09_ms7c0000gn/T/python-build.20160915114035.27423
Results logged to /var/folders/jz/m2f2bdxj1qx9j9xnq09_ms7c0000gn/T/python-build.20160915114035.27423.log

Last 10 log lines:
rm -f /Users/eastagile1ba8/.pyenv/versions/2.7.11/share/man/man1/python.1
(cd /Users/eastagile1ba8/.pyenv/versions/2.7.11/share/man/man1; ln -s python2.1 python.1)
if test "xno" != "xno"  ; then \
       		case no in \
       			upgrade) ensurepip="--upgrade" ;; \
       			install|*) ensurepip="" ;; \
       		esac; \
       		 ./python.exe -E -m ensurepip \
       			$ensurepip --root=/ ; \
       	fi
```

On Mac OS X 10.9, 10.10 and 10.11 you may need to set the CFLAGS environment variable when installing a new version in order for configure to find the zlib headers (XCode command line tools must be installed first):

```
CFLAGS="-I$(xcrun --show-sdk-path)/usr/include" pyenv install -v 2.7.7
```

Alternatively, try reinstalling XCode command line tools for your OS (especially if you just upgraded your OS)

```
xcode-select --install
```
