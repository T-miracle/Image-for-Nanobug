# Image

Version **0.6.3** targets the Nanobug internal-test build of 2026-11-02 through the public host SDK. Installation IDs and permissions are preserved. Windows native helpers included in this package use a statically linked runtime.

Local candidate 0.6.2 uses the configurable native `Editor` contract (`ui.code_editor ^2`, `editor.layout ^2`). It requires the matching development host; content, Undo/Redo and existing plugin data are retained. Build this uncommitted candidate with that host, rather than the historical host revision below.


**English** · [简体中文](https://github.com/Nanobug-Editor/Image/blob/main/README.zh-CN.md)

Native SVG source preview and PNG, JPEG, GIF and WebP image display. The stable installation ID is `svg`; the first independent release is `0.6.1`.

The project is named **Image**. The published `v0.6.1` source and ZIP bytes remain frozen; this documentation update does not change the installation ID or replace a release asset.

This repository is the authoritative plugin source. The [marketplace registry](https://github.com/Nanobug-Editor/Plugin-Marketplace) reviews submissions; fixed ZIP packages live in this repository's Releases. Publishing a Release does not list it automatically. Every initial submission and version requires a registry PR and human review.

## Build independently

Use Nanobug built from the commit pinned in host-sdk.json, with the required native toolchain and WASM target already available. Set `$pluginHost` to the absolute path of that executable:

```powershell
# The public host entry supplies its SDK and packages the project without a source copy.
& $pluginHost --plugin-package . --output dist
```

For a WASM project, run `& $pluginHost --plugin-cargo Cargo.toml test --lib` as well. Declarative packages need no empty WASM component. Missing tools are reported, never installed automatically. Before publishing, check permissions, platform claims, capability requirements and the SHA-256 of the complete ZIP. Changed bytes require a new version and review.

## Maintenance and licensing

[Original plugin notes](https://github.com/Nanobug-Editor/Image/blob/v0.6.1/docs/source-readme.md) preserve feature details and prior verification; current source and this README define the independent build. The migration preserves existing IDs, settings and private data. Image retains the `svg` identity.

The Nanobug workspace's Cargo MIT declaration is made explicit in LICENSE. Grammar, icons and native dependencies keep their own licenses and notices. Import a generated ZIP through the native manager, or install from the marketplace after review, and approve its actual permissions.
