# Pelican Eggs

Ready-to-import [Pelican Panel](https://pelican.dev) eggs for Minecraft server software.

| Egg | Type | Downloads from | Java |
|---|---|---|---|
| [Leaf](servers/leaf) | Server · Paper fork | Leaf API | 21 / 25 |
| [ShreddedPaper](servers/shreddedpaper) | Server · multi-threaded Purpur fork | MultiPaper API | 21 / 25 |
| [Velocity-CTD](proxies/velocity-ctd) | Proxy · Velocity fork | GitHub Releases | 25 |

## Installation

1. Open the folder of the egg you want and download the `egg-*.json` file (**Download raw file**).
2. In Pelican, go to **Admin → Eggs** and click **Import**.
3. Select the JSON file and import it.

You can also import an egg via URL using the raw link of the egg file.

After importing, check the README of the egg for the right Java version and recommended settings.

Each folder contains the egg (`egg-*.json`),  and a README with all variables and notes.

## Disclaimer

These eggs are community-made and not affiliated with Leaf, MultiPaper/ShreddedPaper, Velocity-CTD or Pelican. The server software and logos belong to their respective owners.

## Contributing

Found a bug, have an idea or want another egg? [Open an issue](../../issues).

Want to fix or add an egg yourself? [Pull requests](../../pulls) are welcome. Please make sure that:

- the egg imports, installs and starts in Pelican,
- all texts are in English,
- each egg has its own folder with `egg-*.json`, and a `README.md`.
