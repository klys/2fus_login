# 2fus_login

Java login server package for **StarLoco** (2FUS).

This repository appears to be a runtime/distribution project that includes the login server JAR, launch script, config file, and dependency jars.

---

## Repository Contents

- `login.jar` — Main login server binary
- `Login.bat` — Windows launcher
- `config.properties` — Server/database/network config
- `libs/` — Java dependencies
- `Logs/` — Runtime logs
- `autre/` — Alternate/related packaged artifacts

---

## Requirements

- **Java 8+** in `PATH`
- Access to configured MySQL instance (`database.login.*` in config)

Check Java:

```bash
java -version
```

---

## Run

### Windows

```bat
Login.bat
```

Launcher command:

```bat
java -Xmx1024M -jar login.jar -o true
```

### macOS / Linux

```bash
java -Xmx1024M -jar login.jar -o true
```

---

## Configuration

Edit `config.properties` before production use.

Important keys:

- Exchange bridge: `system.server.exchange.ip`, `system.server.exchange.port`
- Login server: `system.server.login.port`, `system.server.login.version`
- DB connection:
  - `database.login.host`
  - `database.login.port`
  - `database.login.user`
  - `database.login.pass`
  - `database.login.name`
- Web endpoint: `web.url`

Current defaults are local/dev-oriented (`127.0.0.1`).

---

## Logs & Troubleshooting

- Check `Logs/` for startup/runtime issues
- Verify DB credentials and DB availability first
- Ensure port conflicts are resolved (e.g., login port `450`)

Common checks:

1. Java version installed and compatible
2. `login.jar` exists
3. Database reachable from host
4. Config values align with your game/exchange services

---

## Notes

- Source code is not currently present in this repository snapshot; it is primarily a packaged runtime.
- If source gets added later, include build steps and development workflow in this README.
