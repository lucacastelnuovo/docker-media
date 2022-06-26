```
# Copy compose files into /opt
cp -rp /opt/pms-scripts/dockerfiles/server/* /opt/

# Stand up each container... (go grab a coffee, this will take a while)
find /opt/ -maxdepth 1 -name "docker*" -type d \( ! -wholename /opt/ \) -exec bash -c "cd '{}' && docker-compose up -d" \;

```
- The Plex docker files can be split into 4 containers with the UnicornTranscoder for Plex project, which allows you to transcode on multiple servers (if you have a lot of traffic). Please read the docker-compose file for details.
**By default, Plex will be stood up in a single container.**

  - If you want to use this setup, just run: `docker-compose up -d --compose-file docker-compose_multi-transcoder.yml` from the `server/docker-plex` directory.
  - If you're going to run multiple transcoders (on other hosts), you just need to run the `plex-transcoder-1` part of the Plex docker-compose.yml file, not all the other containers...

### Useful URLs:
 - Jackett - `http://<server-ip>:9117/UI/Dashboard` - Start here, configure your torrent indexers to start
 - qBittorrent - `http://<server-ip>:8080/` - This is your torrent client, you will ned to configure save-file location, password etc
 - Sonarr - `http://<server-ip>:8988/` - Configure, then add in all your favorite TV series you want to start auto-downloading
 - Radarr `http://<server-ip>:7878/` - Configure Movies you want to start auto-downloading
 - Bazarr `http://<server-ip>:6767/` - Setup your automatic subtitle downloading
 - Plex - `http://<server-ip>:22500/` - **Access Your Plex Media Server!** (via Nginx proxy injecting TVHeadend CSS Fixes) - You should be port-forwarding to this one and sharing with your friends.
 - Ombi - `http://<server-ip>:3579/` - Worth setting up port-forwarding to this one also - It will allow your friends and family to "request" new Series, Movies etc to be added to your server (This way they don't need access to Radarr/Sonarr/Lidarr)
