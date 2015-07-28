# WordNetSQL #

This repository contains code to make an SQL database from WordNet 3.0 (plus the tagged gloss corpus), and a Ruby/Perl library of common functions for accessing that database. It's sometimes used in TRIPS, and can be used with [DeepSemLex](http://github.com/wdebeaum/DeepSemLex). 

The main documentation is in [README.html](README.html), please read the list of prerequisites there.

Note: this code is not related to [WNSQL](http://wnsql.sourceforge.net/). Nor does it include the WordNet data itself (you must download that separately from [the WordNet website](http://wordnet.princeton.edu/); get the 3.0 version, this code has not been updated for 3.1 yet).

WordNet is © Princeton University

WordNet ™® is a registered tradename.
Princeton University makes WordNet available to research and commercial users free of charge provided the terms of the [license](http://wordnet.princeton.edu/wordnet/license/) are followed, and proper reference is made to the project using an appropriate citation.

## Build instructions ##

    ./configure [--with-wordnet=path/to/WordNet-3.0/dict/]
    make
    make install # installs to trips/etc/

Note that if you unpack the WordNet-3.0 package under `/usr/local/share/wordnet/` (which you may need to create), `./configure` will find it. That is, `/usr/local/share/wordnet/WordNet-3.0/` should exist. Otherwise you need to specify `--with-wordnet`, pointing to the `dict/` directory inside the package, with the trailing slash.

Also note that `make` will take a long time the first time, constructing the SQLite3 database `wn.db`, which will be about 300MB due to all the indexes and the gloss corpus.
