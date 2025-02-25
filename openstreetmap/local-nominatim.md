# Running local OpenStreetMap Nominatim serve

It turns out it's probably quicker to build your own OpenStreetMap
Nominatim server than write some kind of load-balancing and result-caching
script if you're in the market for making a couple of hundred queries.

It's helpful to have a desktop-class machine rather than a laptop, but I
could run this in a 24GB Rancher Desktop VM:

```
$ docker run -it \
    --name nominatim -p 8080:8080 \
    -e PBF_URL=https://download.geofabrik.de/australia-oceania/australia-latest.osm.pbf \
    -e REPLICATION_URL=https://download.geofabrik.de/australia-oceania/australia-updates \
    mediagis/nominatim:4.5
```

Once the PBF files have been unpacked and imported into Postgres, you can
wind down the memory requirements of your VM if necessary.

To exit, ctrl-c or `docker stop --name nominatim` and `docker start --name nominatim` to
restart.
