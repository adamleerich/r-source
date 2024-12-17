## Windows build instructions

Everything below should be run from the MSYS2 command window that comes with Rtools44.




### Get the Tcl/Tk bundle for Windows

Check file listing at https://cran.r-project.org/bin/windows/Rtools/rtools44/files/ for current name.

```sh
# From the R source root directory
wget "https://cran.r-project.org/bin/windows/Rtools/rtools44/files/tcltk-6335-6025.zip"
unzip "tcltk-6335-6025.zip"
```



### Build

```sh
# From ./src/gnuwin32/
export PATH=/x86_64-w64-mingw32.static.posix/bin:$PATH
export TAR=/usr/bin/tar
export TAR_OPTIONS="--force-local"
make all
```



### Skip package re-build

```sh
# From ./src/gnuwin32/
make rbuild
```



### Rmath standalone build

```sh
# From ./src/nmath/standalone
make -f Makefile.win
make -f Makefile.win test.exe
make -f Makefile.win test-static.exe
```






## Notes on `make`


### Regex to list targets in a Makefile

```sh
# https://stackoverflow.com/questions/4219255/how-do-you-get-the-list-of-targets-in-a-makefile/61944430#61944430
grep : Makefile | awk -F: '/^[^.]/ {print $1;}'
```



## Source download links

* https://cran.r-project.org/src/base/R-4/R-4.4.2.tar.gz


