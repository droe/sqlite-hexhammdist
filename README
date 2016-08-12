sqlite-hexhammdist - Hamming distance between hex strings in SQLite
Copyright (C) 2016, Daniel Roethlisberger <daniel@roe.ch>


Synopsis
--------
This SQLite extension adds a function hexhammdist() to SQLite.  hexhammdist()
takes two hex strings as arguments and returns the Hamming distance as integer,
that is, the number of bits the two hex strings differ in.  The return value is
undefined if the two strings are not the same length or if the strings contain
anything other than hexadecimal characters (0-9a-fA-F).

One application for calculating the Hamming distance directly in the database
is perceptual hashing.  While the hashing can be done in the calling scripting
language, the actual Hamming calculations need to be done in the database in
order to perform sufficiently well to scale to a large number of pictures.


Usage
-----
To load the extension into an open SQLite database, run the following queries:

  SELECT load_extension('/path/to/sqlite-hexhammdist.so', 'hexhammdist_init');

You can then use the function in SQL queries, for example to find photos which
have a perceptual hash that is close in Hamming distance:

  SELECT photo_id, hexhammdist(photo_hash, ?) AS hd FROM photos WHERE hd <= 9;

When loading extensions from python, the python binary needs to be built with
the --enable-loadable-sqlite-extensions configure argument.  You then need to
enable the loading of extensions using:

  dbconn.enable_load_extension(True)

After that, you can issue the above SELECT statement to load the extension.


