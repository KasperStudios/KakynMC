# KakynMC

> **Суверенный клиент и GUI-лаунчер Minecraft: Java Edition 26.3 на чистом Rust и Vulkan**  
> С нативной поддержкой Ely.by OAuth2, оффлайн-входом без лицензии, автономным конвертером Java-модов и без назойливой рекламы.

[![GitHub Release](https://img.shields.io/github/v/release/KasperStudios/KakynMC?include_prereleases&color=7c3aed)](https://github.com/KasperStudios/KakynMC/releases)
[![Minecraft Java 26.3](https://img.shields.io/badge/Minecraft-Java%2026.3-5D9C3F)](https://minecraft.net/)
[![Rust](https://img.shields.io/badge/Rust-stable-B7410E?logo=rust&logoColor=white)](https://www.rust-lang.org/)
[![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20Windows-2A2470)]()
[![License](https://img.shields.io/badge/License-MIT-3B2F7E)](LICENSE)

---

## ⚡ Особенности KakynMC

1. **Свобода авторизации**:
   - **Microsoft Account**: официальный вход для игры на лицензионных серверах.
   - **Ely.by OAuth2 (PKCE)**: нативный вход через браузер в 1 клик, полная синхронизация скинов и плащей прямо в Vulkan-рантайме.
   - **Offline Mode**: вход по любому никнейму без привязки к лицензии (ограничение Horizon снято).
2. **Два в одном: Полноценный лаунчер и нативный клиент**:
   - **GUI Launcher** на базе GPUI Fast (wgpu): темная тема, управление версиями, профилями, мирами, ресурспаками и скриншотами.
   - **Игровой движок** на Rust: стабильные 150+ FPS, мгновенный старт, ультра-низкое потребление RAM и никакой зависимости от JVM для запуска игры.
3. **Авто-портатор Java-модов (`modport`)**:
   - Автоматическая декомпиляция `.jar` модов Fabric / Forge / NeoForge.
   - Извлечение моделей, текстур, рецептов и локализаций.
   - Модульная генерация Rust-структур (`blocks.rs`, `items.rs`, `events.rs`, `network.rs`).
   - Посев подробных инструкций для локальных AI-агентов (Hermes Agent / Claude Code / Aider) по принципу *«средство не важно — важен результат»*.
4. **Чистый UI без рекламы**:
   - Вырезаны сторонние рекламные баннеры хостингов и мусорные интеграции.

---

## 🚀 Установка и запуск

### Запуск готового лаунчера
Скачайте бинарник для вашей системы из [Releases](https://github.com/KasperStudios/KakynMC/releases):
- **Linux**: `horizon-launcher` (поддерживает Wayland и X11)
- **Windows**: `horizon-launcher.exe`
- **macOS**: `horizon-launcher-macos.dmg`

### Сборка из исходников

```bash
# Клонирование репозитория
git clone --recurse-submodules https://github.com/KasperStudios/KakynMC.git
cd KakynMC

# Сборка лаунчера
cd launcher
cargo build --release --bin horizon-launcher

# Запуск лаунчера
./target/release/horizon-launcher
```

---

## 🧩 Авто-портирование Java-модов в Rust

Сконвертировать любой сторонний Java-мод в нативный Rust-модуль можно одной командой:

```bash
python modport/main.py /path/to/mod.jar --agent
```

Скрипт автоматически декомпилирует байткод, создаст проект с локальными ссылками на движок и запустит Hermes Agent для дописывания недостающей логики с использованием Context7 MCP для поиска документации.

---

## 📄 Лицензия

KakynMC лицензирован под [MIT License](LICENSE).  
Движок основан на разработках Horizon (`horizon-rust/horizon`). Minecraft является товарным знаком Mojang Studios.
