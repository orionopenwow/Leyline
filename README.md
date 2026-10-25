# Leyline

Leyline is an open, peer-to-peer network for playing, hosting and modding community game realms
(3.3.5a). It grew out of [WrathUnleashed](https://github.com/orionopenwow/WrathUnleashed).

- **Play** in your browser (nothing to install) or in a desktop client.
- **Host** a realm from your own PC with one command: `leyline host`. Docker is the only thing it needs.
- **Stay private**: your realm talks out to the Leyline relay, players connect to the relay, and nobody
  sees your home address. No port forwarding.
- **Share** invite links, list your realm on the Leyline realm list (Beacons), and share mods.
- **Open source**, MIT licensed. No game data is in this repo: hosts extract it from their own install,
  on their own PC.

## Quick start: host a realm

macOS or Linux, with Docker running:

```sh
git clone https://github.com/orionopenwow/Leyline.git
cd Leyline/hosting/kit
bash leyline host        # a few questions the first time; safe to run again
bash leyline status      # your invite or join link
```

Windows: double-click `hosting/kit/Host a Wrath realm.bat`. Full guide: `hosting/INSTALL-OPERATE.md`.

To play on a realm, open its join link (`https://relay.<domain>/join/<realm id>`) and follow the page.

## Run the tests

```sh
cd hosting/tests && python3 -m unittest discover -s . -p 'test_*.py'
```

A few tests read files that only the WrathUnleashed repo has (realm profiles, CI workflows, its control
panel); run those there.

## Layout

| Path | What it is |
|---|---|
| `hosting/relay/` | the relay: tunnels for hosts, the join page, the realm listing, per-IP limits |
| `hosting/kit/` | the host kit: the `leyline` command, host scripts, Docker compose |
| `hosting/kit/tools/` | the host agent, setup and self-check (`wuhost`), the shared network code (`wunet`) |
| `hosting/discord/` | the Discord bridge |
| `hosting/tests/` | tests for all of the above |
| `realm/custom/lua_scripts/` | the realm-side scripts the Leyline window and the Discord bridge talk to |
| `stream/fui-web/.../Leyline.lua` | the in-game Leyline window (`/leyline`); it runs inside the WrathUnleashed UI addon |
| `stream/links.py` | short share links for realms, hangouts, queues, mods and players |
| `stream/www-files/art/` | the Leyline art and display font (SIL OFL 1.1) |
| `mods/SPEC.md` | the mod package format |

The Mods & Workshop panel (`ModsPanel.lua`) uses the rest of the WrathUnleashed UI addon, so it stays in
WrathUnleashed; the in-game window here opens from it.

## Where this comes from

This repo is copied from [WrathUnleashed](https://github.com/orionopenwow/WrathUnleashed) by its
`tools/leyline-repo/export.py`. Send changes there: anything changed only here is replaced on the next copy.

- WrathUnleashed: https://github.com/orionopenwow/WrathUnleashed
- The mod format and template: https://github.com/orionopenwow/WrathUnleashed/tree/main/mods

## License

MIT (see `LICENSE`). Third-party parts and their licenses: `THIRD-PARTY-NOTICES.md`.
