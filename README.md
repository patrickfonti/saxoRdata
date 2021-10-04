## Overview

Example data for package [saxoR](https://github.com/patrickfonti/saxoR/)

## Installation

To install, use the `devtools` package (you might need to install `devtools` first using `install.packages("devtools")`, if you do not have it already):

Note: this might take a while, since the package is > 200 MB

```
devtools::install_github("patrickfonti/saxoRdata")
```

### Install errors

If the above fails, you might need to increase the `timeout` option first, because of the large file size.

```
# increase timeout (better for large files)
options(timeout = max(300, getOption("timeout"))) 

# then run again
devtools::install_github("patrickfonti/saxoRdata")
```

If this still fails, you can try to split download and install:

```
# increase timeout (better for large files)
options(timeout = max(300, getOption("timeout"))) 

# local temporary file for download
tmpfile <- tempfile(fileext = ".zip")

# download package to file
# NOTE: might take some time, since >200 MB
download.file("https://github.com/patrickfonti/saxoRdata/archive/master.zip", tmpfile)

# install from local file
devtools::install_local(tmpfile)
```
