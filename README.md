# BattleHack 2015

A static archive of the 2015 BattleHack site, served at
[battlehack2015.betta.io](https://battlehack2015.betta.io). It was
2015.battlehack.betta.io until October 2026, when betta.io moved to Cloudflare,
whose free certificate only covers one level below betta.io.

## Hosting

The site is the plain files at the root of this repo, served by nginx on
jiji, Cristiano's home server, behind its Cloudflare tunnel. `nginx.conf`
keeps Netlify's URL rules: `/london` and `/london/` both serve
`london/index.html`.

A push to `master` runs `.github/workflows/publish.yml`: CI, then the image
`ghcr.io/betta-apps/2015.battlehack.org`, which it pins in jiji's `docker-compose.yml` to
deploy. `scripts/check.sh` checks every local link resolves;
`scripts/smoke.sh` builds the image and boots it.
