# Changelog

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
