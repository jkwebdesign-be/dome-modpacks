# Dome modpacks

Modpack files for the [Dome](https://www.joindome.be) servers.

They live here rather than with the website because the site is served
from Cloudflare, which caps a single static file at 25 MiB — and a full
content pack clears that on its own.

## Releases

One release per season, tagged by season.

| Season | Tag | File | Minecraft |
|---|---|---|---|
| [Dome SMP S2](https://github.com/jkwebdesign-be/dome-modpacks/releases/tag/s2) | `s2` | `dome-smp2-1.21.1.mrpack` | 1.21.1, Fabric |

## Linking to a pack

Always link the **per-season** URL:

```
https://github.com/jkwebdesign-be/dome-modpacks/releases/download/s2/dome-smp2-1.21.1.mrpack
```

Never `/releases/latest/`. "Latest" follows whichever release is newest,
so publishing S3 would silently repoint every S2 link at the wrong pack.

## Rebuilding a pack

Replace the file under the same release, so the link on the website
never changes:

```
gh release upload s2 dome-smp2-1.21.1.mrpack --repo jkwebdesign-be/dome-modpacks --clobber
```

The `.mrpack` is built on the server and is not stored in the server
repo, so a rebuild needs uploading here as well as dropping into the
server root. This repo is where the website points.

## Installing

In the Modrinth app: **Create new instance** → **Upload modpack**, and
pick the `.mrpack`. The [season page](https://www.joindome.be/seasons/s2/) has
the full mod list, the server address and the setup guide.

Servers are whitelist only — ask in the Discord to be added.
