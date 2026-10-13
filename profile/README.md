# Sysadmin labs

Modules for nginx, built and tested on FreeBSD and Linux.

## nginx modules

Eleven dynamic modules.  Every one of them has the same checks: the release
matrix of nginx versions, a FreeBSD virtual machine, address and undefined
behaviour sanitizers, valgrind, eight reloads in a row, CodeQL, shellcheck
and actionlint — and one more that belongs to that module alone, from a
hostile client to a collector that takes its datagrams apart.

| Module | What it does |
|---|---|
| [nginx-form-input-module](https://github.com/sysadmin-labs/nginx-form-input-module) | Parses `application/x-www-form-urlencoded` request bodies into nginx variables |
| [nginx-gridfs-module](https://github.com/sysadmin-labs/nginx-gridfs-module) | Serves files out of MongoDB GridFS, byte ranges included |
| [nginx-iconv-module](https://github.com/sysadmin-labs/nginx-iconv-module) | Converts between character encodings with `iconv(3)`: a value into a variable, or a whole response body |
| [nginx-json-status-module](https://github.com/sysadmin-labs/nginx-json-status-module) | Reports the connection and request counters and every upstream as one JSON object |
| [nginx-let-module](https://github.com/sysadmin-labs/nginx-let-module) | Evaluates an arithmetic or string expression into a variable |
| [nginx-postgres-module](https://github.com/sysadmin-labs/nginx-postgres-module) | Queries PostgreSQL directly and answers with text, JSON or a status code |
| [nginx-redis2-module](https://github.com/sysadmin-labs/nginx-redis2-module) | Sends commands to Redis and answers with the raw reply |
| [nginx-sflow-module](https://github.com/sysadmin-labs/nginx-sflow-module) | Samples requests and sends them as sFlow datagrams |
| [nginx-slowfs-cache-module](https://github.com/sysadmin-labs/nginx-slowfs-cache-module) | Caches files served from a slow filesystem onto a fast one |
| [nginx-websockify-module](https://github.com/sysadmin-labs/nginx-websockify-module) | Bridges a WebSocket to a plain TCP service, a VNC server for example |
| [nginx-zstd-module](https://github.com/sysadmin-labs/nginx-zstd-module) | Zstandard: an output filter, and a server for precompressed `.zst` files |

Some of these were written here.  The rest were taken over because the
repositories they came from stopped moving, in some cases a decade ago, while
the FreeBSD ports tree still pointed at them.  Each repository's `LICENSE`
says whose code is in it; where that is somebody else's licence, it is theirs
and it stayed.

Each repository has a `CHANGELOG.md`, a release, and build instructions in
its README.

## nginx, and the rest of the family

nginx is what is built and tested in continuous integration today, against
the releases the FreeBSD ports tree ships.  Angie and OpenResty are of
interest and are not tested here yet.

## Links

- Blog and write-ups: [blog.bsdproject.de](https://blog.bsdproject.de)
- Bugs and requests: issues on the repository in question

## License

Each module carries the licence of its own code, and the `LICENSE` in its
repository is the one that applies — three of them are not BSD, because
their authors chose otherwise.  What was written here, including the build
and test scaffolding, is BSD 2-Clause.
