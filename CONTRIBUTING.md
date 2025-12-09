## Goals

- document real silent install and uninstall methods
- capture version patterns and installation sequences
- add known caveats, notes, and prerequisites
- stop rediscovering the same pain repeatedly
- major version > update > new
- custom scripts can be supplied, but prefer supplied
- the automation here is in simple records

This project is **not meant to be perfect**—this is a shared notebook.



## How to Contribute

### 1. Fork the repo and clone it
Create a branch and make your changes.



### 2. Add or update a manifest
Follow the format described in `schema.md`.  

Place manifests under:
/manifests/<Publisher>/<Product>/<Product>-<Version>.json



### 3. Mark uncertain sections honestly
If you are unsure:
- set `"review.reviewed": false`
- add `"inferred": true`
- or use `"UNKNOWN_*"` placeholders

Do **not** invent version strings, GUIDs, or switches.



### 4. Add caveats whenever useful
Caveats and warnings are valuable:
"caveats": [
"Uninstall command fails if service is still running.",
"bundle.xml location may vary"
]




### 5. Avoid sensitive info
Please remove:
- customer names
- tenant IDs
- internal server paths
- personal usernames
- licensing details

Use generic paths when possible.



### 6. Keep descriptions short
This is a reference, not official docs.



## Confirmation

If you have tested a manifest and confirmed it works:
- set `"review.reviewed": true`
- add your GitHub username as `"review.reviewedBy"`
- add a date



## Pull Requests

- keep changes focused
- update only what you know
- add comments where assumptions are made
- small PRs are totally fine



## Philosophy

This repository is intentionally imperfect.
It is a shared memory space for enterprise packaging pain.
Every correction improves life for many other engineers.

Thanks for contributing!
