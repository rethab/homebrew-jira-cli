# homebrew-jira-cli

Homebrew tap for [rethab/jira-cli](https://github.com/rethab/jira-cli).

## Installation

```sh
brew install --cask rethab/jira-cli/jira-cli
```

Homebrew expands the tap name `rethab/jira-cli` to this repository, so no explicit `brew tap` is needed.

On Linux, the `--cask` flag is required: binary casks are installable there, but Homebrew does not resolve them implicitly the way it does on macOS.

## How this tap is maintained

`Casks/jira-cli.rb` is **generated** — it is written and committed by GoReleaser from the release workflow in the [jira-cli](https://github.com/rethab/jira-cli) repository whenever a `v*` tag is pushed. It carries the version, the per-platform download URLs, and their SHA-256 checksums, all of which change on every release.

Do not edit it by hand; the next release will overwrite it. Change [`.goreleaser.yml`](https://github.com/rethab/jira-cli/blob/main/.goreleaser.yml) instead.

## Verifying what you install

The cask pins the SHA-256 of every release archive, and Homebrew checks it on download. The archives themselves carry SLSA build provenance, so you can independently verify that what the cask points at was built by the release workflow in [rethab/jira-cli](https://github.com/rethab/jira-cli) from the tagged commit:

```sh
gh attestation verify <downloaded-archive>.tar.gz --repo rethab/jira-cli
```
