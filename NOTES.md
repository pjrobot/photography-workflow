# Development Notes

## Status: In Progress

## Session 1 — 2026-06-26

### Completed

- Defined the full stack (see README)
- Installed all GUI apps via Pop!_Shop (Flatpak): DigiKam, Darktable, Rapid Photo Downloader
- Installed CLI tools via apt: stow, rclone, docker.io, docker-compose-v2
- Scaffolded repo structure: .gitignore, docker/docker-compose.yml, docker/.env.example
- MariaDB running in Docker on localhost:3306
- DigiKam connected to MariaDB, library root at ~/Pictures, WAL mode enabled

### Decisions Made

- SQLite → MariaDB migration skipped; started directly on MariaDB
- Darktable config (luarc, Lua scripts, styles) deferred until editing workflow is ready
- Immich deferred until photos land on the NAS
- Google Drive mount (via GNOME/GVFS) available for use as RPD source — rclone not needed for selective ingest
- Photos will be ingested gradually from Google Drive into ~/Pictures using RPD, building a clean new structure rather than inheriting Google Drive organisation

### Next Steps

- [ ] Test RPD ingest from Google Drive mount into ~/Pictures
- [ ] Verify DigiKam picks up ingested photos automatically
- [ ] Commit repo to GitHub
- [ ] Eventually: migrate MariaDB to home server, point DigiKam at NAS mount
