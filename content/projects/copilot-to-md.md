---
title: "Github Copilot Export JSON to Markdown Converter "
date: 2025-06-02
---

A converter from GitHub Copilot JSON exports to Markdown. It ships as a Python
script and as an Obsidian plugin, because the conversion is useful both in a
pipeline and inside the vault where the notes end up.

## What it does

- Converts every JSON file in an input directory to Markdown in an output
  directory.
- Creates the output directory if it is missing.
- Extracts the fields that carry the conversation and keeps code blocks
  intact.
- Runs inside Obsidian from a ribbon icon or the command palette.
- Takes input and output folders from configuration.
- Runs anywhere Python does, and anywhere Obsidian does.

## Usage

Python: put the JSON files in `jsons/` and run `python3 json_to_md.py`. The
Markdown lands in `markdowns/`.

Obsidian: copy the plugin folder into the vault, enable it, and convert from
the ribbon icon or the command palette.

Input is a JSON file of Copilot conversation data; output is a Markdown file
with the requests, the responses and the code blocks.

## Licence

GNU GPL v3.0. Source:
[copilot-export-json-to-markdown](https://github.com/FPGArtktic/copilot-export-json-to-markdown).
