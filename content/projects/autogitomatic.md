---
title: "AutoGit-o-Matic"
date: 2025-06-02
---

AutoGit-o-Matic keeps the same work in step across however many computers
it lives on. It is a single POSIX shell script — no Bash, Python or
library required — tested under `dash`, `bash --posix` and `busybox sh`,
and it runs unattended from cron or systemd.

## What it does

- Pulls (`--ff-only`) or fetches across a set of repositories in one run,
  discovered by scanning directories rather than listed by hand.
- Mirrors (`[MIRROR]`) or bundles (`[BUNDLE]`) repositories for carrying
  across an air gap — USB, optical disc or a data diode — with a
  `SHA256SUMS` manifest and submodules followed through `.gitmodules`.
- Fast-forwards branches nobody has checked out (`[SILENT_UPDATE]`),
  without ever touching a work tree.
- Reports status (`--status`) or what the machine can do (`--self-check`)
  without changing anything.
- Runs several repositories at a time (`--jobs N`), locks per
  configuration file so overlapping cron jobs cannot collide, and never
  hangs on credentials.
- Logs as plain text or JSON, with a one-line summary every run ends on.

## Usage

```sh
./autogit-o-matic.sh                         # default configuration
./autogit-o-matic.sh --dry-run --verbose     # report, change nothing
./autogit-o-matic.sh --status                # what every repo looks like
./autogit-o-matic.sh --jobs 4 --log-file autogit.log
```

Hourly, from cron:

```
0 * * * * /path/to/autogit-o-matic.sh --log-file /path/to/autogit.log
```

Or as a systemd timer — `contrib/systemd/` ships a ready-made `.service`
and `.timer` with `Persistent=true`, so a machine that was asleep catches
up instead of waiting for the next hour.

## Versions

Picked up again in October 2026 after sitting at the original Bash
`v1.0.0` since May 2025: rewritten in POSIX `sh`, with a test suite, a
lint gate and CI across four shells. `2.0.0` and `3.0.0` are the breaking
releases; everything else is additive. See
[CHANGELOG.md](https://github.com/FPGArtktic/AutoGit-o-Matic/blob/main/CHANGELOG.md)
for what each release changed.

## Licence

GNU GPL v3.0. Source:
[AutoGit-o-Matic](https://github.com/FPGArtktic/AutoGit-o-Matic).
