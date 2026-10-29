# SplitDPI-presets

[Türkçe](README.tr.md)

Preset data for [SplitDPI](https://github.com/KadirBerkpolat1/SplitDPI): which
zapret2 strategies to try for each ISP and country, which hosts belong to each
app, and which domains are never touched.

SplitDPI ships a copy of this data in its binary. `sudo splitdpi presets update`
downloads `presets.tar.gz` from the latest release here, checks every file, and
uses it instead of the built-in copy. `splitdpi scan` then tries the strategies
for your ISP first, then your country's, then the generic ones.

Each release is tagged with the date in `VERSION`. A file that fails the checks
is skipped, never used.

To add an ISP, fix a strategy or extend an app's hosts, read
[CONTRIBUTING.md](CONTRIBUTING.md). The data is MIT-licensed; sources are
credited in [NOTICE](NOTICE).
