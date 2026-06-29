# Homebrew Caddy

[Homebrew Core](https://github.com/Homebrew/homebrew-core) already provides Caddy, but the formula doesn't install `xcaddy` which is needed to build Caddy plugins.

This is just a simple Tap that clones the [caddy.rb](https://github.com/Homebrew/homebrew-core/blob/main/Formula/c/caddy.rb) formula but adds the `cloudflare-dns` plugin.

## To install:

```
brew uninstall caddy
brew tap mezza/caddy
brew install mezza/caddy/caddy
```

## Editing Caddyfile

Edit `/opt/homebrew/etc/caddy/Caddyfile` and ensure to specify the cloudflare DNS plugin. This snippet assumes, you've put your Cloudflare API token in `/Users/johndoe/.secret/cf_api_token`:

```
tls {
	dns cloudflare {file./Users/johndoe/.secrets/cf_api_token}
}
```

If you're also using hosts on a tailnet, then add this snippet to the relevant hosts block in your Caddyfile:
```
tls {
	get_certificate tailscale
}
```

## To update:

```
brew update
brew upgrade mezza/caddy/caddy
```

## Upgrades:

I am watching the releases at [caddy releases](https://github.com/caddyserver/caddy/releases) and will update the `url`, `sha256` and `version` in the formula as needed, but feel free to open an issue if I've missed a release.
