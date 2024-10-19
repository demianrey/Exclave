# Exclave

A fork of SagerNet, the universal proxy toolchain for Android written in Kotlin.

## Download

- [Exclave](https://github.com/dyhkwong/Exclave/releases/latest)

- [NaïveProxy plugin (use upstream releases directly)](https://github.com/klzgrad/naiveproxy/releases)

- [Hysteria 2 plugin](https://github.com/dyhkwong/Exclave/releases?q=hysteria-plugin-2)

- [Mieru plugin](https://github.com/dyhkwong/Exclave/releases?q=mieru-plugin-3) or [use upstream releases directly](https://github.com/enfein/NekoBoxPlugins/releases)

- [Brook plugin](https://github.com/dyhkwong/Exclave/releases?q=brook-plugin)

- [Juicity plugin](https://github.com/dyhkwong/Exclave/releases?q=juicity-plugin)

- [Other plugins](https://github.com/dyhkwong/Exclave/releases/tag/0.12.0-0-legacy-plugins)

</details>

## Report issues

Please report issues [here](https://github.com/dyhkwong/Exclave/issues). Because the core used in Exclave is heavily modified, do not report issues to upstream. If you think your issue contains sensitive information, encrypt with [this GPG public key](https://github.com/dyhkwong.gpg) before posting.

## License

```
Copyright (C) 2021 by nekohasekai <contact-sagernet@sekai.icu>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
```

## Build
- Install and configure JDK, Android SDK, Android NDK, Go and Go Mobile.
- `git clone` this project and at least submodule `library/core`.
- Replace `release.keystore` (can be generated by Java `keytool`) with your own.
- Append these to your `local.properties`
```
KEYSTORE_PASS=your_keystore_pass
ALIAS_NAME=your_alias_name
ALIAS_PASS=your_alias_pass
```
- Build app:
  - Build libcore:
    ```
    ./run lib core
    ```
  - Download assets:
    ```
    ./gradlew :app:downloadAssets
    ```
  - Build app:
    ```
    ./gradlew :app:assembleOssRelease
    ```
  - APK files will be located in `app/build/outputs/apk/`.
- Build a plugin:
  - Build plugin binaries (the next command already includes this command):
    ```
    ./run plugin [plugin_name]
    ```
  - Build plugin:
    ```
    ./gradlew :plugin:[plugin_name]:assembleOssRelease
    ```
  - Plugin APK files will be located in `plugin/[plugin_name]/build/outputs/apk/`.
