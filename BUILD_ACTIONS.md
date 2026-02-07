# Build pokecrystal with GitHub Actions

This repo includes a GitHub Actions workflow that builds `pokecrystal.gbc` **only** when you provide your own clean Crystal ROM via a GitHub Actions secret. The ROM is reconstructed in CI and never committed to the repo.

## 1) Create the `BASEROM_GBC_B64` secret

You must base64-encode your clean `baserom.gbc` and store it as a GitHub Actions secret named `BASEROM_GBC_B64`.

### Windows PowerShell

```powershell
[Convert]::ToBase64String([IO.File]::ReadAllBytes("baserom.gbc")) | Set-Content -NoNewline baserom.b64
