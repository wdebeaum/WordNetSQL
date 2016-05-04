# WordNetSQL #

This repository contains code to make an SQL database from WordNet 3.0 (plus the tagged gloss corpus), and a Ruby/Perl library of common functions for accessing that database. It's sometimes used in TRIPS, and can be used with [DeepSemLex](http://github.com/wdebeaum/DeepSemLex). 

The main documentation is in [README.html](README.html), please read the list of prerequisites there.

Note: this code is not related to [WNSQL](http://wnsql.sourceforge.net/). Nor does it include the WordNet data itself (you must download that separately from [the WordNet website](http://wordnet.princeton.edu/); get the 3.0 version, this code has not been updated for 3.1 yet).

WordNet is © Princeton University

WordNet ™® is a registered tradename.
Princeton University makes WordNet available to research and commercial users free of charge provided the terms of the [license](http://wordnet.princeton.edu/wordnet/license/) are followed, and proper reference is made to the project using an appropriate citation. Again, WordNetSQL does not include WordNet itself, so that license does not apply to this code; see the licensing section below.

## Build instructions ##

    ./configure [--with-wordnet=path/to/WordNet-3.0/dict/]
    make
    make install # installs to trips/etc/

Note that if you unpack the WordNet-3.0 package under `/usr/local/share/wordnet/` (which you may need to create), `./configure` will find it. That is, `/usr/local/share/wordnet/WordNet-3.0/` should exist. Otherwise you need to specify `--with-wordnet`, pointing to the `dict/` directory inside the package, with the trailing slash.

Also note that `make` will take a long time the first time, constructing the SQLite3 database `wn.db`, which will be about 300MB due to all the indexes and the gloss corpus.

## Licensing ##

WordNetSQL is licensed using the [GPL 2+](http://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html) (see `LICENSE.txt`):

WordNetSQL - makes an SQL DB from WN, and includes a library for accessing it
Copyright (C) 2016  Institute for Human & Machine Cognition

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.
