# LumiLocalization

📖 English | [中文版](README_zh.md)

Lumi 家族应用与 Swift Package Manager 插件包共用的本地化查找包。

## 产品

- `LumiLocalizationKit`

## 用法

添加包依赖：

```swift
.package(url: "https://github.com/lumi-softworks/LumiLocalization.git", from: "1.0.0")
```

将产品加入目标并导入：

```swift
.product(name: "LumiLocalizationKit", package: "LumiLocalization")
```

```swift
import LumiLocalizationKit

let title = LumiLocalization.string("settings.title", bundle: .module)
```

查找时会先检查请求的 `.lproj` 字符串表，再检查对应的 `.xcstrings` 目录；
若无匹配译文则返回键本身。中文的文种与地区变体使用回退链。
结果按 bundle、表名、键与 locale 缓存。
