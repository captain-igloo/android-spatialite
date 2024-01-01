# android-spatialite 

## What is this?
The [Spatialite](https://www.gaia-gis.it/gaia-sins/) database ported for *Android*

## When do I need it?
- When you need deployment, collecting, processing and fast querying of small to huge amounts of geometry data (points, polylines, polygons, multipolygons, etc.) on Android devices.
- When you want to be 100% independent from any server/cloud backend.

## Getting Started

If you know basic *SQLite*, there's almost nothing to learn. The API is 99% the same as the Android *SQLite* API (as of API level 15). The main difference is the packaging. Use `io.requery.android.database.*` instead of `android.database.*`.

## Other FAQ

### What is *Spatialite*?
Simply: *Spatialite* = *SQLite* + advanced spatial support.
It is an *SQLite* extension which adds the ability to store and query spatial data.  For more info: https://www.gaia-gis.it/fossil/libspatialite/index

### Does it use JDBC?
No. It uses cursors - the suggested lightweight approach to access SQL used in the Android platform instead of the heavier JDBC.

### Reducing the APK size. 

This library is distributed as multi-architecture AAR file. 
By default Gradle will produce a universal APK including the native .so libraries compiled for all supported CPU architectures. Usually that's unacceptable for large libraries like this.
But that's easily fixed by using Gradle's "ABI splits" feature. The following gradle code will produce a separate APK per each architecture. The APK size is reduced few times.
```
android {
    splits {
        abi {
            enable true
                reset()
                include "armeabi-v7a", "arm64-v8a", "x86", "x86_64"
            }
        }
    }
}
```

### What libraries are packaged currently?

- GEOS 3.12.0
- iconv 1.17
- Proj 9.3.0
- Spatialite 5.1.0
- SQLite 3.43.0

## Requirements
Min SDK 16

## Credits

The main ideas used here were borrowed from:
- https://github.com/requery/sqlite-android

## LICENSE
Apache License 2.0
