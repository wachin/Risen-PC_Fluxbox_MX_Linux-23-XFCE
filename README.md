# Fluxbox diagnostics and fixes for Qt/KDE dialogs

Date: 2026-07-14


## Changes applied

### 1. Transient dialog focus rule

File: `~/.fluxbox/apps`

Added a Fluxbox `[transient]` rule:

```text
[transient] (Class=^(kate|kdenlive|dolphin|dmidiplayer|ksnip)$)
  [FocusProtection] {Gain,Lock}
[end]
```

Reason:

- `[transient]` applies to modal/dialog windows with `WM_TRANSIENT_FOR`.
- `Gain` tells Fluxbox that the new dialog is allowed to take focus when it opens.
- `Lock` prevents another window from stealing focus immediately while the modal dialog is active.

This is more targeted and less invasive than changing the global focus model for all windows.


