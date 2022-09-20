# Powkiddy folder hierarchy

> NOTE: this repo only contains the folder hierarchy, **DON'T** contains any type of **ROM**.

The SD card used must be formatted on: **FAT** or **FAT32**.

Structure extracted from:

Model: `X51`

Version: `2.0.00.220505.2349`

## TL;DR

* Under SD card root:

```bash
git clone https://github.com/mcrx0/powkiddy-folder-hierarchy
rm -rf .git/ README.md
```

# Notes

When a new ROM is added to collection, this must have the same name that folder container.

```bash
game/
  |-- ps/
  |  |-- Biohazard 3/
  |  |   |-- Biohazard 3.img
  |  |
  |  |-- Dino Crisis 2/
  |  |   |-- Dino Crisis 2.img
  |  |
  |  |-- [...]
  |
  |-- [...]
```

> NOTE: every emulator folder have its own `images/` folder, place on it the cover game.

Each game cover must be have the same name as folder.

```bash
game/
  |-- ps/
     |-- Biohazard 3/
     |   |-- Biohazard 3.img
     |
     |-- images/
     |   |-- Biohazard 3.png
```

Inside `game/.date/` folder you must see some files, all with termination `*.js`.
It's an simple array nested on an object, that' contains info about ROMs installed.

> Example: `ps.js`

```javascript
{
    "list": [
        {
            "soupin": "Biohazard 3",
            "child": false,
            "title": "Biohazard 3",
            "url": "/mnt/card/game/ps/Biohazard 3/Biohazard 3.img"
        },
        { ... },
    ]
}
```

To generate this files, you need to go settings on your Powkiddy: `System Setup > Sync Game filelist`
