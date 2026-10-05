---
title: "GnuRAMage - The GNU RAM Disk Synchronization Tool"
date: 2025-06-02
---

GnuRAMage keeps a RAM disk and a hard disk in step. It is written in Bash and
aimed at RAM disks large enough to hold a working set — multi-terabyte ones —
where losing the contents to a crash or a power cut is a real cost rather than
a theoretical one.

## What it does

- Copies files from disk to the RAM disk on start.
- Syncs changes back to persistent storage on an interval, so a crash costs at
  most one interval.
- Excludes files and directories by pattern.
- Reads an INI configuration file.
- Logs at several levels, with an error-only log for unattended runs.
- Has a dry-run mode that reports what it would do and changes nothing.
- Has a one-shot mode for a single cycle.
- Verifies with checksums, optionally.
- Generates standalone scripts for cron and other schedulers.
- Syncs once more on SIGINT and SIGTERM before exiting.

## Why

A RAM disk is fast and volatile. Keeping it in step with disk by hand is both
tedious and the kind of task that is skipped exactly when it matters. This
automates it, and the dry-run and checksum modes exist so the automation can
be checked rather than trusted.

## Requirements

- Bash 4.0 or newer
- rsync
- GNU/Linux
- Enough RAM to make the exercise worthwhile

## Usage

```sh
./gramage.sh                            # default configuration
./gramage.sh --dry-run --verbose        # report, change nothing
./gramage.sh --config mysetup.ini       # custom configuration
./gramage.sh --script-gen-only          # emit automation scripts and exit
```

## Licence

GNU GPL v3.0. Source:
[GnuRAMage](https://github.com/FPGArtktic/GnuRAMage).
