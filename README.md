# HyDE Settings

A searchable settings hub for [HyDE](https://github.com/HyDE-Project/HyDE): one
place to find HyDE's own tools and the system settings programs already on a
HyDE install (Audio, Displays, Network, Appearance, Accounts, Firewall, ...),
instead of having to remember which separate app each one lives in.

Most entries resolve to tools HyDE already ships or recommends (Pavucontrol,
nwg-displays, nm-connection-editor, nwg-look, font-manager, Flatseal,
`kcmshell6` for KDE KCMs, ...) and just give them one searchable front door,
rather than reimplementing each one's UI. A few things are built in directly:
a read-only account overview, a copyable system-information page, and a
weather-location search for Waybar's weather module.

See [`docs/manual.md`](docs/manual.md) for the full manual and
[`docs/tests.md`](docs/tests.md) for the acceptance matrix behind the test
suite.

## Deployment

This repo is deployed as a HyDE dot via `deez` -- see `Scripts/dots/settings.toml`
in the [HyDE repo](https://github.com/HyDE-Project/HyDE). It isn't meant to be
run standalone outside a HyDE install (it depends on `hyde-shell`,
HyDE's Wallbash colours, and other HyDE-specific state).

## Testing

```sh
python3 tests/settings_test.py          # logic checks
python3 tests/settings_test.py --gtk    # + GTK integration checks (needs Xvfb)
```

Requires Python 3.11+, GTK 3 and PyGObject for the GTK checks.

## License

GPLv3, same as HyDE -- see [LICENSE](LICENSE).
