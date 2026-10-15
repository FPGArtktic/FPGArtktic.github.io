---
title: "gpygap"
date: 2026-10-15
---

gpygap builds an offline PyPI mirror for air-gapped networks: the top
1000 projects plus your own packages, every dependency, extra and build
requirement, for several Python versions and platforms. Developers on
the far side of the gap install with `uv` or `pip` exactly as they would
from PyPI.

## What it does

- Builds wheels in a container, while it still has a toolchain, for any
  project that publishes none for a target platform — so installing
  offline is a plain binary install.
- Verifies every package before it ships: an offline install check for
  every requirement, Python version and platform, with anything missing
  fetched and checked again.
- Ships extras (`uvicorn[standard]`, `celery[redis]`, ...) on by default.
- Synchronizes like `rsync --delete`: new versions and the current top
  list land, dropped projects leave with the dependencies nobody else
  needs.
- Exports deltas with checksums, so only changes cross the air gap and a
  damaged transfer is caught before it touches the offline mirror.
- Runs entirely in a rootless Podman container; nothing is built or
  installed on the host.
- Tested on every push by installing from the mirror offline, on a real
  container of each target: Debian, Ubuntu, RHEL (UBI), Arch, Alpine and
  Windows.

## Usage

```bash
bin/gpygap sync --top 10       # smoke run: ~1 GB, ~5 minutes
bin/gpygap sync --plan-only    # size of the full mirror, nothing downloaded
GPYGAP_MOUNTS=/media/usb bin/gpygap sync --export-delta /media/usb/delta-2026-10
```

Offline, applying a delta needs nothing but Python 3.9+:

```bash
python3 /media/usb/delta-2026-10/gpygap_offline.py apply /media/usb/delta-2026-10 /srv/gpygap
```

## Limitations

CPython only, and a Linux host cannot cross-build a Windows wheel — those
come from what the project publishes, plus whatever the mirror already
built as `py3-none-any`. What is left is listed by name in
`MIRROR-GAPS.json`.

## Licence

GPL-3.0-or-later. Source and documentation:
[gpygap](https://github.com/FPGArtktic/gpygap) ·
[docs](https://gpygap.readthedocs.io/en/latest/).
