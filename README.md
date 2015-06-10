
# minjur

Osmium-based converter of OSM data to GeoJSON.


## Prerequisites

You need [libosmium](https://github.com/osmcode/libosmium) installed.


## Compile

To setup:

    mkdir build
    cd build
    cmake ..

Usually this should do the trick. If you need more configuration call

    ccmake .

Compile with

    make


## Run

Run like this:

    minjur OSMFILE >out.geojson

Call with `--help` to see command line options.


## Working with updates

Run like this:

    export INDEX=sparse_mmap_array
    minjur -d -l $INDEX OLD_OSMFILE >out.geojson
    minjur-generate-tilelist -l $INDEX,locations.dump CHANGE_FILE >tiles.list
    minjur -d -l $INDEX -t tiles.list NEW_OSMFILE >changes.geojson

Or, on the planet:

    export INDEX=dense_mmap_array
    ...

## Name

This project is named after the town of Minjur in India which I know nothing
about.

https://www.openstreetmap.org/#map=15/13.2781/80.2530

