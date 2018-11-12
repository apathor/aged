# NAME
aged - Find files sorted by timestamp metadata.

# SYNOPSIS
aged [OPTIONS] [DIRECTORY ...]

Print all files in given directory trees sorted by time of last access, change,
 or modification. Files are sorted by access time from oldest to newest by default.

OPTIONS:
 -a -c -m    : Sort by time last of access, change, or modification.
 -l          : Include columns for date and time.
 -n NUMBER   : List only the first NUMBER lines.
 -r          : Reverse sort order, newest files first.
 -p GLOB     : Print only files matching GLOB.
 -y INTERVAL : Show files younger than INTERVAL.
 -z INTERVAL : Show files older than than INTERVAL.

# EXAMPLES
Show the least and most recently accessed file here.

`$ aged -n1; aged -r -n1`

Show the path and timestamp of the ten most recently modified files "~/foo".

`$ aged -m -l -n10 ~/foo`

Show files modified more than two days but less than three weeks ago.

`$ aged -m -z 2d -y 3w`

View the six most recently accessed JPEGs in the given directory.

`$ feh -Z -f <(aged -a -n6 -p '*.jpg' ~/img/)`

Play the oldest OGG video in the given directory.

`$ mpv $(aged -m -p '*.ogg' -n1 ~/videos/)`

# AUTHOR
Mike Lalumiere 2018

# License
GPLv3 (see LICENSE)
