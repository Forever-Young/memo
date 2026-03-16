---
name: apple-notes
description: Manage Apple Notes via the `memo notes api` CLI on macOS (create, view, edit, delete, search, move, and export notes). Non-interactive, machine-friendly API for scripts and AI agents.
homepage: https://github.com/Forever-Young/memo
metadata:
  {
    "openclaw":
      {
        "emoji": "📝",
        "os": ["darwin"],
        "requires": { "bins": ["memo"] },
        "install":
          [
            {
              "id": "brew",
              "kind": "brew",
              "formula": "forever-young/tap/memo",
              "bins": ["memo"],
              "label": "Install memo via Homebrew",
            },
          ],
      },
  }
---

# Apple Notes API

Use `memo notes api` to manage Apple Notes from the terminal. Non-interactive, machine-friendly commands for scripts and AI agents. Output is plain text, well-parsable (TSV, lines, JSON).

## Setup

- Install (Homebrew): `brew tap forever-young/tap && brew install forever-young/tap/memo`
- Manual (pip): `pip install .` (after cloning the repo)
- macOS-only; if prompted, grant Automation access to Notes.app.

## List Notes

- List all notes: `memo notes api list`
- Filter by folder: `memo notes api list -f "Folder Name"`
- Output formats: `--format tsv` (default), `lines`, `json`

## Create Notes

- Add note from stdin: `echo "# Title\nBody" | memo notes api add -f "Folder Name"`

## View Notes

- Show note body as Markdown: `memo notes api show <note-id>`

## Edit Notes

- Replace note body from stdin: `memo notes api edit <note-id>` (pipe or redirect)

## Delete Notes

- Delete a note: `memo notes api delete <note-id>`

## Move Notes

- Move note to folder: `memo notes api move <note-id> <target-folder>`

## Search Notes

- Search by title: `memo notes api search "query"`
- Search in body too: `memo notes api search "query" --body`
- Filter by folder: `memo notes api search "query" -f "Folder"`

## Folders

- List folders: `memo notes api folders`
- Delete folder: `memo notes api remove <folder-path> --force`

## Export

- Export all notes: `memo notes api export --path /path/to/dir`
- With Markdown conversion: `memo notes api export --path /path/to/dir --markdown`

## Limitations

- macOS-only. Requires Apple Notes.app.
- For automation, grant permissions in System Settings > Privacy & Security > Automation.
