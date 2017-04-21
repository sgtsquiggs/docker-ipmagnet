[![](https://images.microbadger.com/badges/image/sgtsquiggs/ipmagnet.svg)](https://microbadger.com/images/sgtsquiggs/ipmagnet)

# ipmagnet

This image is derived from [sgtsquiggs/alpine.nginx](https://hub.docker.com/r/sgtsquiggs/alpine.nginx/).

[ipMagnet](https://github.com/cbdevnet/ipmagnet) allows you to quickly check what adresses your BitTorrent client is handing out to its Trackers.

## Usage
```
docker run \
    --name=ipmagnet \
    -v <path to data>:/config \
    -e PGID=<gid> -e PUID=<uid> \
    -p 80:80 \
    sgtsquiggs/ipmagnet
```

## Parameters
* `-p 80:80` external port 80 mapping to internal port 80
* `-v <path>:/config` where configuation files are stored.
* `-e PGID=<gid>` for Group ID (see below)
* `-e PUID=<uid>` for User ID (see below)
* `-e PUBLIC_URL=<url>` publicly accessable url. Needs trailing slash! Defaults to http://localhost:80/

## User and Group ID
Set these to match the user/group ID of shared data volumes. Files written to these volumes will match the
provided uid/gid.

## Acknowledgements

* [lsiobase/alpine.nginx](https://github.com/linuxserver/docker-baseimage-alpine-nginx)
