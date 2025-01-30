# Benchmarks of JavaScript Package Managers

**Last benchmarked at**: _Jan 29, 2025, 12:34 PM_ (_daily_ updated).

This benchmark compares the performance of npm, pnpm, Yarn Classic, and Yarn PnP (check [Yarn's benchmarks](https://yarnpkg.com/benchmarks) for any other Yarn modes that are not included here).

Here's a quick explanation of how these tests could apply to the real world:

- `clean install`: How long it takes to run a totally fresh install: no lockfile present, no packages in the cache, no `node_modules` folder.
- `with cache`, `with lockfile`, `with node_modules`: After the first install is done, the install command is run again.
- `with cache`, `with lockfile`: When a repo is fetched by a developer and installation is first run.
- `with cache`: Same as the one above, but the package manager doesn't have a lockfile to work from.
- `with lockfile`: When an installation runs on a CI server.
- `with cache`, `with node_modules`: The lockfile is deleted and the install command is run again.
- `with node_modules`, `with lockfile`: The package cache is deleted and the install command is run again.
- `with node_modules`: The package cache and the lockfile is deleted and the install command is run again.
- `update`: Updating your dependencies by changing the version in the `package.json` and running the install command again.

## Lots of Files

The app's `package.json` [here](https://github.com/pnpm/pnpm.io/blob/main/benchmarks/fixtures/alotta-files/package.json)

| action  | cache | lockfile | node_modules| npm | pnpm | Yarn | Yarn PnP |
| ---     | ---   | ---      | ---         | --- | ---  | ---  | ---      |
| install |       |          |             | 27.5s | 8.5s | 9.3s | 5.6s |
| install | ✔     | ✔        | ✔           | 1.4s | 894ms | 5s | n/a |
| install | ✔     | ✔        |             | 7.9s | 2.5s | 5.2s | 1.3s |
| install | ✔     |          |             | 11.9s | 5.7s | 9.4s | 5.1s |
| install |       | ✔        |             | 10.5s | 5.2s | 5.3s | 1.3s |
| install | ✔     |          | ✔           | 1.6s | 2.1s | 9.1s | n/a |
| install |       | ✔        | ✔           | 1.3s | 906ms | 5s | n/a |
| install |       |          | ✔           | 1.6s | 5.1s | 9.1s | n/a |
| update  | n/a | n/a | n/a | 6.2s | 3.3s | 6.1s | 5.1s |

<img alt="Graph of the alotta-files results" src="/img/benchmarks/alotta-files.svg" />