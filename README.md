# hub-cli

Signed release binaries of hub-cli, the command-line client for the Briteweb Hub.

## Install

```bash
curl -fsSL https://hub.briteweb.com/cli/install.sh | sh
```

```powershell
irm https://hub.briteweb.com/cli/install.ps1 | iex
```

```bash
brew tap briteweb-ltd/hub-cli https://github.com/Briteweb-Ltd/briteweb-hub-cli-releases && brew install --cask hub-cli
```

```powershell
scoop bucket add hub-cli https://github.com/Briteweb-Ltd/briteweb-hub-cli-releases && scoop install hub-cli
```

## Update

```bash
hub-cli update
```

## Verify a download

```bash
cosign verify-blob --bundle hub-cli_<version>_checksums.txt.sigstore.json \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com \
  --certificate-identity https://github.com/Briteweb-Ltd/briteweb-hub-cli/.github/workflows/release.yml@refs/tags/v<version> \
  hub-cli_<version>_checksums.txt
```
