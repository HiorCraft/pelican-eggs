# Leaf

<img src="icon.png" width="80" align="right" alt="Leaf logo">

Leaf is an open-source, high-performance server software designed for Minecraft and built on top of Paper. By focusing on performance, vanilla behavior and stability, Leaf aims to provide a fast and highly customizable server that stays fully compatible with Spigot and Paper plugins.

**Egg file:** [`egg-leaf.json`](egg-leaf.json)<br>
**Project:** [leafmc.one](https://www.leafmc.one) · [GitHub](https://github.com/Winds-Studio/Leaf)

## Variables

| Name | Variable | Default | Description |
|---|---|---|---|
| Minecraft Version | `MINECRAFT_VERSION` | `latest` | Minecraft version to install, e.g. `26.2` or `1.21.8` |
| Build Number | `BUILD_NUMBER` | `latest` | Leaf build to install |
| Server Jar File | `SERVER_JARFILE` | `server.jar` | Name of the server jar |

## Java version

| Minecraft version | Docker image |
|---|---|
| 26.x | Java 25 *(default)* |
| 1.21.x | Java 21 |

## How it works

- The installer uses the official Leaf download API (`api.leafmc.one`) to find the requested version and build.
- If the version doesn't exist, it lists all available versions.
- If the download fails, your existing server jar is restored.

## Notes

- At the time of writing, Leaf only publishes **experimental builds**. Make a backup before switching an existing server.
- **Behind Velocity:** set `online-mode=false` in `server.properties`, enable `proxies.velocity` in `config/paper-global.yml` and add your Velocity forwarding secret there.
