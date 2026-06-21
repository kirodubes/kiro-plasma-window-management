# Changelog

## 2026.06.21

### What Changed
- Fixed the lost 4th virtual desktop. The `[Desktops] Id_*` keys had been dropped
  from `etc/xdg/kwinrc` as "machine-specific", but KWin reconciles the virtual
  desktop count by the `Id_N` entries (not `Number` alone), so it collapsed the
  4th desktop on login.

### Technical Details
- Re-added `Id_1`…`Id_4` to the `[Desktops]` block using portable, non-machine-specific
  strings (`Desktop-1`…`Desktop-4`) rather than the original captured UUIDs — keeps the
  config portable while making `Number=4` stick.

### Files Modified
- `etc/xdg/kwinrc`
- `CLAUDE.md` (corrected the "Id_* dropped" note)

## 2026.06.20

### What Changed
- Initial repo created in the Kiro ecosystem: default KWin window-management config
  for the Plasma edition (currently window rules).
- Renamed `kiro-plasma-kwin-rules` → `kiro-plasma-window-management` (broader scope;
  GitHub repo, local dir, recipe, and ECOSYSTEM entry all updated).
- Standard markdown scaffold added (`README.md`, `CHANGELOG.md`, `CLAUDE.md`).
- Canonical bash scaffold copied in (`up.sh`, `setup.sh`) plus `LICENSE`, `kiro.jpg`,
  `.gitignore`.
- Captured `etc/xdg/kwinrc` from the box — minimal KWin window-management default:
  4 virtual desktops (2 rows), effects on (cube / slide-back / wobbly + tuning),
  titlebar-wheel → Maximize/Restore, Flipswitch alt-tab, bottom-left edge → Show Desktop.
  Dropped machine-specific `[Desktops] Id_*` UUIDs and `[Tiling][uuid]` blocks.
- **Consolidation:** this package is now the **single owner of `kwinrc`** — the
  `[ElectricBorders]` key was moved here out of `kiro-plasma-system-settings` so two
  packages don't both ship `/etc/xdg/kwinrc` (pacman file conflict).
- Window rules (`kwinrulesrc`) remain in scope but none defined yet (box `rules=` empty).
- Git initialised with the kirodubes SSH remote; repo created on GitHub.

### Files Modified
- README.md, CHANGELOG.md, CLAUDE.md (created)
- up.sh, setup.sh, LICENSE, kiro.jpg, .gitignore (copied)
- etc/xdg/.gitkeep (placeholder)
