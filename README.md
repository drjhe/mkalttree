# mkalttree
Takes a tree of audio files (typically FLACs) and clones it into another
directory, transcoded to a target codec. Converts multiple files in parallel.

```
usage: mkalttree.py [-h] [-c] [-f] [-X] [-j PROCESSES] [-n] [-l] [-q] {mp3,opus} SRCDIR DESTDIR

Transcodes a tree of audio files

positional arguments:
  {mp3,opus}            output codec
  SRCDIR                source base directory
  DESTDIR               destination base directory

options:
  -h, --help            show this help message and exit
  -c, --no-covers       don't copy cover art files
  -f, --force           also process up-to-date files
  -X, --ignore-exclude  ignore .exclude files
  -j PROCESSES, --jobs PROCESSES
                        number of processes to spawn
  -n, --dry-run         don't actually produce files
  -l, --copy-lossy      don't transcode lossy sources
  -q, --quiet           suppress progress output
```
