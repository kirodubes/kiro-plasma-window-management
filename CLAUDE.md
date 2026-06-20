# CLAUDE.md — kiro-plasma-kwin-rules

## Project overview

See [README.md](./README.md). Ships the default **KWin window rules**
(`kwinrulesrc`) for Kiro's Plasma edition.

## Current state

Created 2026-06-20. Standard Kiro bash scaffold (`up.sh`, `setup.sh`) plus the
three required markdown files. Payload dir `etc/xdg/` is an empty placeholder —
**no window rules captured yet** (the box's `kwinrulesrc` had an empty `rules=`).
Set rules in System Settings → Window Management → Window Rules, then capture from
the box into `etc/xdg/kwinrulesrc`.

## Patterns & decisions

- Planned delivery is `/etc/xdg/kwinrulesrc` (XDG cascade), consistent with
  `kiro-plasma-system-settings` / `kiro-plasma-dolphin`. Verify the cascade honors
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
