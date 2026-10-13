# BattleHack 2015

A static archive of the 2015 BattleHack site, served at
[2015.battlehack.betta.io](https://2015.battlehack.betta.io).

## Hosting

The site is the plain files at the root of this repo, served by nginx on
jiji, Cristiano's home server, behind its Cloudflare tunnel. `nginx.conf`
keeps Netlify's URL rules: `/london` and `/london/` both serve
`london/index.html`.

A push to `master` runs `.github/workflows/publish.yml`: CI, then the image
`ghcr.io/cbetta/2015.battlehack.org`, which it pins in jiji's `docker-compose.yml` to
deploy. `scripts/check.sh` checks every local link resolves;
`scripts/smoke.sh` builds the image and boots it.
