# BesterLauncher

[Русский](#русский) · [English](#english)

![BesterLauncher logo](src/BesterLauncher/Assets/logo_cube.png)

## Русский

**Minecraft Java и Bedrock — в одном лаунчере для Windows.** BesterLauncher написан на C# и WPF; интерфейс, сборки и настройки рассчитаны на то, чтобы запускать игру и управлять модами из одного места.

**Текущая версия: 1.7.0.**

> Неофициальный проект. Не связан с Mojang Studios или Microsoft.

## Возможности

- **Minecraft Java Edition:** релизы, снапшоты и старые версии; профили Vanilla, Fabric, Forge, NeoForge и Quilt.
- **Сборки:** поиск и избранное, независимое копирование, импорт модпаков, полные резервные копии `.besterpack` с мирами и настройками.
- **Каталог контента:** моды, модпаки, ресурспаки и шейдеры с Modrinth и CurseForge. Для CurseForge требуется собственный API-ключ.
- **Minecraft for Windows (Bedrock):** установка и обновление при наличии лицензии Microsoft; вход через учётную запись Microsoft.
- **Аккаунты и скины:** Microsoft для официальной авторизации; поддерживаются оффлайн-режим и сторонние authlib-injector-серверы. Скины можно хранить и редактировать в лаунчере.
- **Серверы и сеть:** список серверов, проверка статуса, Aternos во встроенном браузере и совместная игра через сетевую вкладку.
- **Настройки:** Java, ОЗУ, JVM-аргументы, фон и оформление. Токены аккаунтов защищаются Windows DPAPI; пароли Microsoft не сохраняются лаунчером.

## Скачать

- [Установщик BesterLauncher 1.7.0](release/BesterLauncher-Setup-1.7.0.exe) — рекомендуемый вариант; установщик проверит наличие .NET 8 Desktop Runtime.
- [Портативный EXE](release/BesterLauncher.exe) — требуется .NET 8 Desktop Runtime x64.

Первый переход с версии **1.6.0 на 1.7.0** нужно выполнить вручную: старые версии ещё не содержат автообновлятор.

## Автообновление

В 1.7.0 добавлены проверка HTTPS-манифеста, сверка версии, загрузка установщика и проверка SHA-256. **Автообновление пока не подключено к публичному серверу:** постоянный URL `latest.json` ещё не задан. Для включения нужно настроить `UpdateManifestUrl` в `src/BesterLauncher/Services/LauncherUpdateService.cs` и опубликовать Setup вместе с манифестом. Инструкция: [`UPDATES.md`](UPDATES.md).

Автоматическое обновление поддерживается для установок, зарегистрированных Setup. Портативную копию нужно обновлять вручную.

## Требования

- Windows 10 или новее, x64.
- Для сборки из исходников — .NET 8 SDK и Visual Studio 2022 с workload **.NET desktop development**.
- Для Bedrock необходима лицензия Minecraft в учётной записи Microsoft. Оффлайн-аккаунты предназначены для одиночной игры и серверов, разрешающих `online-mode=false`.

## Сборка из исходников

```bat
build.bat
```

Команда запускает WPF-лаунчер в Debug. Для подготовки релизных файлов используйте `publish.bat`; он собирает портативный EXE, лёгкий EXE и Setup.

## Прозрачность и ограничения

- **Разработка велась с помощью ИИ-инструментов.** ИИ помогал создавать и редактировать код, документацию, тесты и маркетинговые материалы; результат дорабатывался по требованиям проекта. ИИ может ошибаться — проверяйте сборки и тестируйте функции перед использованием.
- Исходники собираются, а отдельные части проверяются автоматическими тестами. Проверка WPF-интерфейса, сценария автообновления и оффлайн-скин-пака в настоящей Minecraft на Windows всё ещё необходима.
- Проверка модов — вспомогательный эвристический анализатор, а не замена антивирусу.
- Перед установкой сверяйте SHA-256 файла релиза. В текущих сборках подпись Authenticode не настроена.
- Файл `LICENSE` пока не добавлен. Не считайте проект лицензированным для свободного копирования или распространения.

Расширенная документация на русском: [`docs/README_RU_DETAILED.md`](docs/README_RU_DETAILED.md).

**Telegram:** https://t.me/besterlauncher  
**TikTok:** https://www.tiktok.com/@besterlauncher

---

## English

**Minecraft Java and Bedrock in one Windows launcher.** BesterLauncher is built with C# and WPF, bringing game versions, modded instances, and launcher settings together in one place.

**Current version: 1.7.0.**

> Unofficial project. Not affiliated with Mojang Studios or Microsoft.

## Features

- **Minecraft Java Edition:** releases, snapshots, and older versions; Vanilla, Fabric, Forge, NeoForge, and Quilt profiles.
- **Instances:** search and favorites, independent duplication, modpack import, and full `.besterpack` backups including worlds and settings.
- **Content catalog:** mods, modpacks, resource packs, and shaders from Modrinth and CurseForge. A personal CurseForge API key is required for CurseForge.
- **Minecraft for Windows (Bedrock):** installation and updates require a valid Microsoft game license and Microsoft account.
- **Accounts and skins:** Microsoft sign-in for official authentication; offline mode and third-party authlib-injector servers are also supported. Store and edit skins in the launcher.
- **Servers and networking:** server list and status checks, Aternos in an embedded browser, and multiplayer through the Network tab.
- **Settings:** Java runtime, memory, JVM arguments, backgrounds, and appearance. Account tokens are protected with Windows DPAPI; Microsoft passwords are not stored by the launcher.

## Downloads

- [BesterLauncher Setup 1.7.0](release/BesterLauncher-Setup-1.7.0.exe) — recommended; the installer checks for .NET 8 Desktop Runtime.
- [Portable EXE](release/BesterLauncher.exe) — requires .NET 8 Desktop Runtime x64.

The first upgrade from **1.6.0 to 1.7.0** must be installed manually; older versions do not include the updater.

## Auto-updates

Version 1.7.0 includes HTTPS manifest checking, version comparison, installer download, and SHA-256 verification. **Automatic updates are not connected to a public release server yet:** a permanent `latest.json` URL has not been configured. To enable it, set `UpdateManifestUrl` in `src/BesterLauncher/Services/LauncherUpdateService.cs` and publish the Setup executable with the manifest. See [`UPDATES.md`](UPDATES.md).

Automatic updates are supported for installations registered by Setup. Portable copies must be updated manually.

## Requirements

- Windows 10 or newer, x64.
- To build from source: .NET 8 SDK and Visual Studio 2022 with the **.NET desktop development** workload.
- Bedrock requires a Minecraft license associated with a Microsoft account. Offline accounts are intended for single-player and servers that allow `online-mode=false`.

## Build from source

```bat
build.bat
```

This starts the WPF launcher in Debug mode. Use `publish.bat` to create the portable EXE, lightweight EXE, and Setup installer.

## Transparency and limitations

- **Development was assisted by AI tools.** AI helped create and edit code, documentation, tests, and marketing materials; the results were adapted to the project requirements. AI can make mistakes—review builds and test features before use.
- The source builds and selected components have automated tests. The WPF interface, updater flow, and offline skin pack still need verification in Minecraft on Windows.
- The mod checker is a heuristic helper, not a replacement for antivirus software.
- Verify release-file SHA-256 before installation. Authenticode signing is not configured for the current builds.
- No `LICENSE` file has been added yet. Do not assume the project is licensed for unrestricted reuse or redistribution.

Extended documentation in Russian: [`docs/README_RU_DETAILED.md`](docs/README_RU_DETAILED.md).

**Telegram:** https://t.me/besterlauncher  
**TikTok:** https://www.tiktok.com/@besterlauncher
