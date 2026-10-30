# SwiftDown

[![codecov](https://codecov.io/gh/qeude/SwiftDown/branch/main/graph/badge.svg?token=RB6K3Q5QIO)](https://codecov.io/gh/qeude/SwiftDown)

> ## 🔀 Maintained fork
>
> This is **[Fletcher-Alderton/SwiftDown](https://github.com/Fletcher-Alderton/SwiftDown)**, a maintained fork of **[qeude/SwiftDown](https://github.com/qeude/SwiftDown)** by Quentin Eude.
>
> The upstream repository has been **archived (read-only) since February 2024** and no longer accepts pull requests, so this fork carries the work forward. The original PR proposing these changes ([qeude/SwiftDown#39](https://github.com/qeude/SwiftDown/pull/39)) is open upstream but can no longer be merged there.
>
> ### What this fork adds
>
> - **New built-in theme: `defaultClear`** — identical to the default light theme, but with a **fully transparent background**. Useful for overlay editors or any UI where the editor should sit on top of an app-supplied background.
> - **Transparent-colour support in the theme/background pipeline** — `SwiftDown` and `SwiftDownEditor` now skip drawing the background when a theme's colour fields contain the word `clear`, so transparent JSON themes render correctly.
> - Added a `default-clear.json` theme and documentation for the clear theme.
>
> Everything else is unchanged from upstream `develop`. This fork stays in sync with upstream where possible and is the recommended package URL going forward.

## 📖 Description

A markdown editor component for your SwiftUI apps.

- 🎉 Live preview directly in editor for most of Markdown elements, without web based preview.
- ⚡️ Fast, built on top of [cmark](https://github.com/commonmark/cmark).
- 🗒 Pure markdown, no proprietary format.
- 💻:📱 macOS and iOS support.

<div align=center><img src="resources/demo.gif" align=center height="500"></div>

## 🛠️ Install

### 📦 Swift Package Manager

Either use Xcode to add the package dependency or add the following dependency to your Package.swift:

```
// Upstream (archived):
// .package(url: "https://github.com/qeude/SwiftDown.git", from: "0.4.1"),
// Maintained fork (recommended):
.package(url: "https://github.com/Fletcher-Alderton/SwiftDown.git", from: "0.4.1"),
```

## 🔧 Usage

```swift
import SwiftDown
import SwiftUI

struct ContentView: View {
    @State private var text: String = ""

    var body: some View {
        SwiftDownEditor(text: $text)
            .insetsSize(40)
            .theme(Theme.BuiltIn.defaultDark.theme())
    }
}
```

## 🖌️ Themes

### 🖼 BuildIn themes

#### Default Dark

<img src="resources/default-dark-theme.png" height="400">

#### Default Light

<img src="resources/default-light-theme.png" height="400">

#### Default Clear (same as light except the background is transperent)

<img src="resources/default-light-theme.png" height="400">

### 🧑‍🎨 Custom themes

SwiftDown supports theming by using config `.json` files as [this one](./Sources/SwiftDown/Resources/Themes/default-dark.json)
Then init your custom theme as below.

```swift
Theme(themePath: Bundle.main.path(forResource: "my-custom-theme", ofType: "json"))
```

## 👨🏻‍💻 Author

- Quentin Eude
  - [Github](https://github.com/qeude)
  - [LinkedIn](https://www.linkedin.com/in/quentineude/)
