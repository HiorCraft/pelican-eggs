# Velocity-CTD

<img src="icon.png" width="80" align="right" alt="Velocity logo">

Velocity-CTD is an open-source fork of the Velocity proxy that adds built-in Redis support, a queue system, network-wide commands and performance optimizations.

**Egg file:** [`egg-velocity-ctd.json`](egg-velocity-ctd.json)<br>
**Project:** [GitHub](https://github.com/GemstoneGG/Velocity-CTD) · [Releases](https://github.com/GemstoneGG/Velocity-CTD/releases)

## Variables

| Name | Variable | Default | Description |
|---|---|---|---|
| Build Number | `BUILD_NUMBER` | `latest` | Velocity-CTD build to install, e.g. `400` (release `build-400`) |
| Jar Type | `JAR_TYPE` | `bootstrap` | `bootstrap` or `fatjar`, see below |
| Server Jar File | `SERVER_JARFILE` | `velocity.jar` | Name of the server jar |

### Jar type

- **`bootstrap`** *(recommended)*: a small jar that downloads its libraries once on the first start.
- **`fatjar`**: contains everything, but Velocity-CTD plans to remove it soon. If a build has no fatjar, the installer uses the bootstrap jar instead.

## Requirements

- **Java 25:** Velocity-CTD is built with Java 25 and won't start on older versions. Java 25 is the default image.
- **Fixed memory limit:** like the official Velocity egg, the startup command uses `-Xmx{{SERVER_MEMORY}}M`. With a memory limit of `0` (unlimited), the proxy can't start.

## How it works

- The installer finds the requested build through the GitHub Releases API.
- Every download is verified against the SHA-256 checksum provided by GitHub.
- The jar is downloaded to a temporary file first, so your existing jar is only replaced after a successful download.
- On the first install, the default `velocity.toml` of the selected build is downloaded, so the panel can set the correct port before the first start. An existing `velocity.toml` is never overwritten.
- The GitHub API allows 60 requests per hour per IP address. If you reinstall very often and the installer can't reach GitHub, wait a moment and try again.

## Notes

- **Modern forwarding:** set `player-info-forwarding-mode = "modern"` in `velocity.toml`. Velocity-CTD creates `forwarding.secret` on the first start. Use its content as the secret on your backend servers.
- **Proxy Protocol:** if a DDoS protection service with Proxy Protocol sits in front of the proxy, set `haproxy-protocol = true`.
- **Switching an existing Velocity server:** back up `velocity.toml` and `forwarding.secret`, change the egg in the admin area, select Java 25 and reinstall.
- The egg uses the Velocity logo, as Velocity-CTD has no logo of its own.
