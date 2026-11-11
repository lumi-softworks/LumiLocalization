# LumiLocalization

📖 English | [中文版](README_zh.md)

A shared localization lookup package for Lumi family apps and Swift Package Manager plugin bundles.

## Product

- `LumiLocalizationKit`

## Use

Add the package dependency:

```swift
.package(url: "https://github.com/lumi-softworks/LumiLocalization.git", from: "1.0.0")
```

Add the product to a target and import it:

```swift
.product(name: "LumiLocalizationKit", package: "LumiLocalization")
```

```swift
import LumiLocalizationKit

let title = LumiLocalization.string("settings.title", bundle: .module)
```

The lookup checks the requested `.lproj` strings table, then the matching `.xcstrings` catalog, and returns the key when no translation is found. Chinese script and region variants use a fallback chain. Results are cached by bundle, table, key, and locale.
