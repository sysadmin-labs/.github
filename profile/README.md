# Sysadmin labs

Tools, modules and plugins from a sysadmin's daily work: web servers, mail,
identity and everything around them. Where an upstream went quiet or a gap
needs closing, it gets fixed, tested and released here.

Built and tested on **FreeBSD and Linux**.

## nginx modules

Dynamic modules for the nginx family. nginx is supported and tested in CI
today, Angie and OpenResty are planned. Every module has its own CI: build
and test, FreeBSD, sanitizers, Valgrind, CodeQL and lint.

| Module | What it does |
|---|---|
| [nginx-form-input-module](https://github.com/sysadmin-labs/nginx-form-input-module) | Parses `application/x-www-form-urlencoded` request bodies into nginx variables |
| [nginx-let-module](https://github.com/sysadmin-labs/nginx-let-module) | Evaluates an arithmetic or string expression into a variable |
| [nginx-zstd-module](https://github.com/sysadmin-labs/nginx-zstd-module) | Zstandard output filter plus a server for precompressed `.zst` files |
| [nginx-slowfs-cache-module](https://github.com/sysadmin-labs/nginx-slowfs-cache-module) | Caches files from a slow filesystem onto a fast one |

Each repository has a `CHANGELOG.md`, tagged releases and build instructions
in its README.

## Links

- Blog and write-ups: [blog.bsdproject.de](https://blog.bsdproject.de)
- Bugs and requests: issues on the repository in question

## License

BSD 2-Clause, see [LICENSE](https://github.com/sysadmin-labs/.github/blob/main/LICENSE).
Projects derived from other work keep the license of their authors, stated
in each repository.
