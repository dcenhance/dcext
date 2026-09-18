# RetroFlash game library

Every Flash file the extension plays, 95 of them, 383.6 MiB in total.

## Layout

Files are not stored in one flat directory: each level of the tree takes one hex digit
of the file's own SHA-256, so **no folder holds more than sixteen entries** and a game
sits 3 levels deep. The path is derived purely from the content, which means the
same file always lands in the same place, and a client that knows a hash can address a
game directly without walking the tree.

```
assets/flash-games/library/0/1/2/snake.swf
```

`catalog.json` lists every game with its path, title, size, SHA-256 and where it was
imported from - use it instead of guessing paths.

## Origin

The initial 95 games were imported from github.com/AmmarSAA/flash-games-directory. They are third-party works
preserved for play; the repository license covers the tooling, not the games
themselves. Newer additions carry their own `imported_from` entry in the catalogue.

## Adding games

Fetch, then let the publisher place them: a file's directory is a function of its
hash, and `catalog.json` is written on every publish, so nothing has to be moved by
hand. Keep an eye on the size - GitHub warns past 1 GB per repository and refuses any
single file over 100 MB.
