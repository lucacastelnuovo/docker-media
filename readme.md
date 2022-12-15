### Installation

```
git clone https://github.com/Luca-Castelnuovo/media.ltc.git && cd media.ltc
mv * ../ && cd ../ && rm -rf media.ltc

cd jackett && docker-compose up -d && cd ..
# open http://10.0.20.20:9117/UI/Dashboard and configure your torrent indexers

cd transmission && docker-compose up -d && cd ..
# open http://10.0.20.20:9091 and configure your torrent client

cd sonarr && docker-compose up -d && cd ..
# open http://10.0.20.20:8988 and configure indexer & download client

cd radarr && docker-compose up -d && cd ..
# open http://10.0.20.20:8988 and configure indexer & download client

cd plex && cp .env.example .env
# set plex claim token in .env

docker-compose up -d && cd ..
# open http://10.0.20.20:32400 and configure your plex server

cd ombi && docker-compose up -d && cd ..
# open http://10.0.20.20:3579 and configure your ombi server
```
