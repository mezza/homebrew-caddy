# Homebrew Caddy

[Homebrew Core](https://github.com/Homebrew/homebrew-core) already provides Caddy, but the formula doesn't install `xcaddy` which is needed to build Caddy plugins.

This is just a simple Tap that clones the [caddy.rb](https://github.com/Homebrew/homebrew-core/blob/main/Formula/c/caddy.rb) formula but adds the `cloudflare-dns` plugin.

## To use:

```
brew uninstall caddy
brew tap mezza9/caddy
brew install mezza9/caddy/caddy
brew services start mezza9/caddy/caddy
```

## To update:

```
brew update
brew upgrade mezza9/caddy/caddy
```

## Upgrades:

I am watching the releases at [caddy releases](https://github.com/caddyserver/caddy/releases) and will update the `url`, `sha256` and `version` in the formula as needed, but feel free to open an issue if I've missed a release.
