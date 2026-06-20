<p align="center">
  <img src="kiro.jpg" alt="Kiro" width="220" />
</p>

# kiro-plasma-window-management

Default **KWin window-management** configuration for Kiro's Plasma edition —
per-application **window rules** (size, position, desktop, floating/maximised state,
no-border, etc.) applied out of the box, with room to grow into broader KWin window
behaviour. Sibling to
[kiro-plasma-system-settings](https://github.com/kirodubes/kiro-plasma-system-settings),
[kiro-plasma-konsole](https://github.com/kirodubes/kiro-plasma-konsole),
[kiro-plasma-dolphin](https://github.com/kirodubes/kiro-plasma-dolphin),
[kiro-plasma-keybindings](https://github.com/kirodubes/kiro-plasma-keybindings) and
[kiro-plasma-servicemenus](https://github.com/kirodubes/kiro-plasma-servicemenus).

## What's in this repo

- `etc/xdg/kwinrc` — the KWin window-management defaults, shipped as a system-wide
  XDG cascade default (read beneath each user's `~/.config/kwinrc`, so it applies to
  every user, is never overwritten, and uninstalls cleanly). Minimal — only the
  intentional keys:
  - **4 virtual desktops**, 2 rows
  - **Desktop effects on**: cube, slide-back, wobbly windows (+ wobbly tuning)
  - **Titlebar mouse-wheel → Maximize/Restore**
  - **Alt-Tab switcher = Flipswitch**
  - Bottom-left screen edge → Show Desktop
- **Window rules** (`kwinrulesrc`) are in scope for this package but none are shipped
  yet — they'll be added here when defined.
- `setup.sh`, `up.sh` — standard Kiro bash scaffold (git identity + sync).

## Installation

### From `nemesis_repo` (recommended)

```ini
[nemesis_repo]
SigLevel = Never
Server = https://erikdubois.github.io/$repo/$arch
```

```bash
sudo pacman -Syu
sudo pacman -S kiro-plasma-window-management
```

### Manual

```bash
git clone https://github.com/kirodubes/kiro-plasma-window-management.git
cd kiro-plasma-window-management
sudo cp -rT etc /etc
```

The file lands in `/etc/xdg/`. Log out and back in for the rules to apply.

## Websites

Information : https://kiroproject.be

## Social Media

Youtube : https://www.youtube.com/erikdubois

<!-- KIRO-FUNDING-FOOTER:START — managed by Kiro-HQ/cascade-readme-footer.sh -->
## Help fund Kiro

Everything I build here stays free and open — always. If Kiro or any of these
tools have ever saved you time or taught you something, a small monthly
contribution helps keep the work going. Donations target break-even, nothing
more — the core always stays free for everyone.

- GitHub Sponsors: https://github.com/sponsors/erikdubois
- Patreon: https://www.patreon.com/c/kiroproject
- YouTube memberships: https://www.youtube.com/@ErikDubois/join
- Ko-fi: https://ko-fi.com/erikdubois
- PayPal: https://www.paypal.me/erikdubois
<!-- KIRO-FUNDING-FOOTER:END -->

## License

See [LICENSE](./LICENSE).
