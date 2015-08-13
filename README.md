# adam-helpers
Scripts for fetching and caching ADAM builds, by version number or git SHA.

## Installation

* Put this repo on your `$PATH`.
* `source` [`.adam-rc`](./.adam-rc) in your `.bashrc` or equivalent.

By default, it will create `~/adams` and download ADAM releases that you select there.

### Optional Configuation

The following environment variables will configure `adam-helpers`' behavior:

* `$ADAM_HELPERS_DIR`: use a directory other than `~/adams` to store ADAM releases.
* `$ADAM_SCALA_VERSION`: defaults to `2.10`; set to `2.11` to use ADAM's Scala 2.11 releases.
  * Note: this will only work for ADAM releases, of which only one is supported at the moment (`0.17.0`).
* `$ADAM_REPO_URL`: set to a clone of the ADAM repo other than git@github.com:bigdatagenomics/adam.git, e.g. a local clone on your filesystem, to enable builds at SHAs that haven't been upstreamed yet.

## Usage

```sh
$ adam-select 0.17.0   # Download the 0.17.0 release, set $ADAM_HOME pointing to it.
$ adam-select f541584  # Clone and build ADAM from f541584, a.k.a. #754.

# Build ADAM from a branch in a local clone.
$ ADAM_REPO_URL=/path/to/my/adam/clone adam-select my-branch 
```

