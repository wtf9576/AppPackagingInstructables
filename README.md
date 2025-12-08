# AppPackagingInstructables
YAML notepad for enterprise apps



This project stores human-friendly JSON manifests describing the way enterprise desktop apps are typically installed, silently, and uninstalled.
It is not authoritative, and it is not vendor-supported. It is a community knowledge base.

# Why this exists

### Some software is packaged the same way across many years, many orgs, and many versions—yet every packaging engineer has to rediscover:

- silent switches
- deployment flags
- detection rules
- uninstall methods
- known caveats
- missing GUIDs
- weird requirements

### This manifest format captures and shares that knowledge even if it’s not perfect.

## “Confirmed vs Inferred”
- confirmed = explicitly observed from actual install media
- inferred = pattern-based guess from similar versions
- unknown = left blank on purpose
- placeholder = strings like UNKNOWN_*

### This is a knowledge capture format, not a guarantee.

## Status Flags
- false	likely needs validation
- true	someone tested & confirmed
- null	TBD
When filling blanks

## Always prefer:
- honesty
- placeholders
- comments

“I think it works with all Windows versions but I’m not sure”

Do NOT invent GUIDs or claim accuracy you don’t have.
