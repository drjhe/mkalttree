# mkalttree
Takes a tree of audio files (typically FLACs) and clones it into another
directory, transcoded to a target codec. Converts multiple files in parallel.

```
usage: mkalttree [-h] [-c] [-f] [-X] [-j PROCESSES] [-n] [-l] [-q] {mp3,opus} SRCDIR DESTDIR

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

## Codec support

| Codec   | Input | Output |
|---------|-------|--------|
| FLAC    | Yes   | No     |
| MP3     | Yes   | Yes    |
| Opus    | Yes   | Yes    |
| Vorbis  | Yes   | No     |
| AAC     | Yes   | No     |

Codec support is controlled by the ```CODEC_TABLE``` global dictionary in
```mkalttree```. See the comments above it for a description of the format and
how to add codecs or change the transcoding command.

## Requirements
In its default configuration, this script requires:
 - ffmpeg (with libmp3lame for MP3 support)
 - opus-tools
