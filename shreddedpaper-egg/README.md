# ShreddedPaper

<img src="icon.png" width="80" align="right" alt="MultiPaper logo">

ShreddedPaper is an open-source, multi-threaded Purpur fork that brings vertical scaling to Minecraft by running a single world on multiple threads.

**Egg file:** [`egg-shreddedpaper.json`](egg-shreddedpaper.json)<br>
**Project:** [GitHub](https://github.com/MultiPaper/ShreddedPaper) · [Downloads](https://multipaper.io/shreddedpaper/download.html)

## Variables

| Name | Variable | Default | Description |
|---|---|---|---|
| Minecraft Version | `MINECRAFT_VERSION` | `latest` | Minecraft version to install, e.g. `26.2` or `1.21.11` |
| Build Number | `BUILD_NUMBER` | `latest` | ShreddedPaper build to install |
| Server Jar File | `SERVER_JARFILE` | `server.jar` | Name of the server jar |

## Java version

| Minecraft version | Docker image |
|---|---|
| 26.x | Java 25 *(default)* |
| 1.21.11, 1.20.6 | Java 21 |

## How it works

- The installer uses the official MultiPaper download API (`api.multipaper.io`) to find the requested version and build.
- Every download is verified against the SHA-256 checksum from the API.
- The jar is downloaded to a temporary file first, so your existing server jar is only replaced after a successful download.
- If a version or build doesn't exist, the installer lists the available ones.

## Notes

- **Give it more than one CPU core.** ShreddedPaper spreads a world across multiple threads. With a CPU limit of `100` (one core) you lose that advantage. Set the server's CPU limit to e.g. `400` (four cores) or `0` (unlimited).
- **Plugins:** plugins that already support Folia will most likely work without changes. Other plugins may run into threading issues, so test them first.
- **Public beta:** according to its developers, ShreddedPaper is in public beta. Make backups.
- **Behind Velocity:** set `online-mode=false` in `server.properties`, enable `proxies.velocity` in `config/paper-global.yml` and add your Velocity forwarding secret there.
- The egg uses the MultiPaper logo, as ShreddedPaper has no logo of its own.
