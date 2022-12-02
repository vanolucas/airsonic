[Airsonic](https://airsonic.github.io/) web media streamer.

[linuxserver/airsonic-advanced](https://hub.docker.com/r/linuxserver/airsonic-advanced) Docker image.

# Build & Run using `docker-compose`

Set your configuration in the [.env](.env) file:
- `LOCAL_MUSIC_DIR`: path to the directory that contains all your audio files.
- `LOCAL_PORT`: port to expose this web server. Use `127.0.0.1:<PORT>` for local-only.
- `TIMEZONE`: your local timezone.
- `PUID`: local user id to map to the container's internal user.
- `PGID`: local group id to map to the container's internal group.

Example:
```
LOCAL_MUSIC_DIR=/home/vanolucas/Music
LOCAL_PORT=8080
TIMEZONE=Europe/Brussels
PUID=1000
PGID=1000
```

Then run `docker-compose` in this directory containing [docker-compose.yml](docker-compose.yml):
```bash
docker-compose up -d
```

Browse to the container's URL. e.g. [http://localhost:8080/](http://localhost:8080/).

# Use Airsonic

See [Airsonic documentation](https://airsonic.github.io/docs/) for more detail.

# Stop

```bash
docker-compose down
```

# TODO

- [ ] add script that constructs the playlist file to the image
- [ ] construct playlist of all audio files on build