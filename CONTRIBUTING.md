# Contributing to SplitDPI-presets

These files tell [SplitDPI](https://github.com/KadirBerkpolat1/SplitDPI) which
zapret2 strategies to try for each ISP and which hosts belong to each app.
SplitDPI fetches the latest release with `sudo splitdpi presets update`.

## Layout

```
VERSION                      release date, YYYY-MM-DD
isp/<cc>/as<N>-<slug>.toml   one ISP: name, country, asn list, source, reported, [[strategy]]
apps/<id>.toml               one app: id, name, hosts, probe, quic, optional [udp], note
countries/<cc>.toml          default_apps, exclude file, optional [[strategy]]
generic.toml                 [[strategy]] tried after the ISP and country ones
exclude/global.txt           domains never desynced, one per line
exclude/<cc>.txt             the same, per country
```

Every TOML file starts with `schema = 1`.

## Strategy strings

A strategy is space-separated nfqws2 options. Only `--payload`, `--lua-desync`,
`--in-range`, `--out-range` and `--blob=<name>:0x<hex>` are accepted, and only
desync functions shipped with the pinned zapret2. Anything else (files, filters,
`--lua-init`, Lua code) makes SplitDPI skip the whole file.

## Before you open a pull request

1. Run `splitdpi presets check .` and fix every file it names.
2. For a new or changed ISP strategy, set `reported` to the month a user
   confirmed it works, and say in the pull request how you tested it
   (`splitdpi doctor`, `splitdpi probe`, the app itself).
3. Credit the source in `source` and, for new data sets, in `NOTICE`.

## Releases

Bump `VERSION` to today's date and push a tag with the same name, for example
`git tag 2026-10-28 && git push --tags`. The release workflow checks the data
and publishes `presets.tar.gz`.

Contributions are accepted under the MIT License (see `LICENSE`).
