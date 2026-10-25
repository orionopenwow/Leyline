# Third-party notices

Leyline's own code is MIT licensed (`LICENSE`). These parts come from elsewhere or work with outside software:

- **Leyline display font** (`stream/www-files/art/leyline-display.woff2`): Big Shoulders Display,
  SIL Open Font License 1.1. The license is next to it: `stream/www-files/art/leyline-display-OFL.txt`.
- **Ed25519 fallback** (`hosting/kit/tools/wunet/ed25519_pure.py`): from the Open Vanilla launcher, the same
  project, MIT.
- **SRP6 test vectors** (`hosting/tests/test_crypto.py`): from a public MIT-licensed SRP test corpus.
- **AzerothCore** (AGPL-3.0): the realm images the host kit runs are built from AzerothCore and its modules.
  No AzerothCore source is in this repo; its sources are at https://github.com/azerothcore.
- **Game data**: none here. Hosts extract dbc and map files from their own 3.3.5a install, on their own PC,
  and they never leave it.
