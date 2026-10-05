---
title: "AutoGit-o-Matic"
date: 2025-06-02
---

AutoGit-o-Matic runs git operations across many repositories at once. It is a
Bash script, and it exists because the same work living on several machines
means several repositories drifting out of date in different directions.

## What it does

- Pulls or fetches across a set of repositories in one command.
- Finds repositories by scanning directories, rather than requiring a list.
- Reads an INI file for which repositories to manage and how to log.
- Writes logs as plain text or JSON.
- Has a dry-run mode that reports what it would do and changes nothing.
- Has a verbose mode that reports each operation.
- Runs unattended from cron.

## Usage

```sh
./autogit-o-matic.sh                             # default configuration
./autogit-o-matic.sh --dry-run --verbose         # report, change nothing
./autogit-o-matic.sh --config myconfig.ini       # custom configuration
./autogit-o-matic.sh --log-file autogit.log      # log to a file
```

Hourly, from cron:

```
0 * * * * /path/to/autogit-o-matic.sh --log-file /path/to/autogit.log
```

## Licence

GNU GPL v3.0. Source:
[AutoGit-o-Matic](https://github.com/FPGArtktic/AutoGit-o-Matic).
