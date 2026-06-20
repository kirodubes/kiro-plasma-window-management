# CLAUDE.md — kiro-plasma-window-management

## Project overview

See [README.md](./README.md). Ships the default **KWin window-management**
configuration for Kiro's Plasma edition — currently the window rules
(`kwinrulesrc`), with room to grow into broader KWin window behaviour.

## Current state

Created 2026-06-20. Standard Kiro bash scaffold (`up.sh`, `setup.sh`) plus the
three required markdown files. `etc/xdg/kwinrc` ships a **minimal** KWin
window-management default captured from the box: 4 virtual desktops (2 rows),
effects on (cube / slide-back / wobbly + tuning), titlebar-wheel → Maximize/Restore,
Flipswitch alt-tab, bottom-left edge → Show Desktop. **This package is the single
owner of `kwinrc`** — the `[ElectricBorders]` key was moved here out of
`kiro-plasma-system-settings` (2026-06-20) to avoid two packages owning
`/etc/xdg/kwinrc`. Dropped from the capture: machine-specific `[Desktops] Id_*`
UUIDs and all `[Tiling][uuid]` blocks (not portable). Window rules (`kwinrulesrc`)
are in scope but none defined yet.

## Patterns & decisions

- Delivery is `/etc/xdg/kwinrc` (XDG cascade), consistent with
  `kiro-plasma-system-settings` / `kiro-plasma-dolphin`. Cascade for `kwinrc` is
  verified (the `system-settings` session ran the `kreadconfig6` sentinel test).
  When window rules are added later, verify the cascade honors
  `kwinrulesrc` (the `[General] rules=` list + per-rule `[uuid]` groups) with the
  `kreadconfig6` sentinel test before relying on it — window rules use a list+groups
  structure, so if the cascade merge is unreliable, fall back to `/etc/skel`.
  See [[kde-config-delivery-and-servicemenus]].
- Bash scripts follow the canonical Kiro template — see
  [up.sh](/home/erik/Insync/Kiro/Kiro-HQ/up.sh) / [setup.sh](/home/erik/Insync/Kiro/Kiro-HQ/setup.sh).

## Next steps

- Capture the real `kwinrulesrc` once rules exist on the box.
- Add the build recipe under `~/KIRO-PKG-BUILD-APPS/` (copies `etc/` into the package).

Open work for the ecosystem lives in
[HQ/MASTER_TODO.md](/home/erik/Insync/Kiro/Kiro-HQ/MASTER_TODO.md) — no per-repo TODO.md.
