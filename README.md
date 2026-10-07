# HeroUpdate

`heroupdate` installs the newest [HeroineOS](https://github.com/HeroineOS) components from
their GitHub releases: HeroBar, HeroLauncher, HeroAppearance, HeroWallpaper, HeroPortal
(and the HeroUI demos if you have them). It only downloads what's newer than what's
installed, installs it all with one `apt install`, and restarts what was running (the old
versions would keep running otherwise).

```sh
mkdir -p ~/.local/bin
curl -fsSL https://raw.githubusercontent.com/HeroineOS/HeroUpdate/main/heroupdate -o ~/.local/bin/heroupdate
chmod +x ~/.local/bin/heroupdate
heroupdate
```

```
heroupdate               check, ask, download, install, restart
heroupdate --check       only list what's newer
heroupdate --yes         don't ask
heroupdate --with-demos  include heroui-demos
heroupdate --self-update get the newest heroupdate
```

It's a POSIX shell script needing only `curl`, `dpkg` and `apt` (and `sudo` to install).
GitHub allows 60 unauthenticated API requests an hour; a run uses one per component.

A signed apt repository (`sudo apt upgrade` doing all of this) is planned; this is the
stopgap until then.
