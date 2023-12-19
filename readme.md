### Installation

```
git clone https://github.com/lucacastelnuovo/docker-media.git && cd docker-media
mv * ../ && cd ../ && rm -rf media.ltc

cd jackett && docker-compose up -d && cd ..
# open http://10.0.20.20:9117/UI/Dashboard and configure your torrent indexers

cd transmission && docker-compose up -d && cd ..
# open http://10.0.20.20:9091 and configure your torrent client

cd sonarr && docker-compose up -d && cd ..
# open http://10.0.20.20:8988 and configure indexer & download client

cd radarr && docker-compose up -d && cd ..
# open http://10.0.20.20:8988 and configure indexer & download client

cd plex && docker-compose up -d && cd ..
# open http://10.0.20.20:32400 and configure your plex server

cd ombi && docker-compose up -d && cd ..
# open http://10.0.20.20:3579 and configure your ombi server
```
