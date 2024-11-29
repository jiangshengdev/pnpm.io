---
id: pack
title: pnpm pack
---

Create a tarball from a package.

## Options

### --pack-destination &lt;dir\>

Directory in which `pnpm pack` will save tarballs. The default is the current working directory.

### --pack-gzip-level &lt;level\>

Specifying custom compression level.

### --json

Log output in JSON format.

## Life Cycle Scripts

* `prepack`
* `prepare`
* `postpack`

