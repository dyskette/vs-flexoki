# Flexoki for Visual Studio

Flexoki Dark and Light for Visual Studio 2026, for the window chrome and the editor. Colours from [Flexoki](https://stephango.com/flexoki), syntax as in its [Sublime Text scheme](https://github.com/kepano/flexoki-sublime). Anything not set here comes from the built-in Dark or Light theme.

## Install
Download [`Flexoki.vsix`](https://github.com/dyskette/vs-flexoki/releases/latest/download/Flexoki.vsix) from the latest release (its SHA256 is in `Flexoki.vsix.sha256`) and open it, with Visual Studio closed. Then pick **Flexoki Dark** or **Flexoki Light** in Tools > Options > Environment > Visual Experience, or both as the system dark and light themes under **Use system setting**.

## Build
`msbuild Flexoki.csproj /restore /p:Configuration=Release` builds `bin/Release/net48/Flexoki.vsix`; it needs Visual Studio's MSBuild and the .NET Framework 4.8 targeting pack.

## Change colours
Edit `FlexokiDark.vstheme` and `FlexokiLight.vstheme`. Colours are `AARRGGBB`. Token names are on Tools > Options > Environment > Visual Experience > Theme colors (chrome) and Fonts and Colors (syntax).

## Release
Bump `Version` in `source.extension.vsixmanifest`, then push a matching tag (`v1.0.1` for `1.0.1`). The `Build` workflow builds every push and pull request, and publishes the VSIX for a tag; it fails if the tag and the manifest disagree.
