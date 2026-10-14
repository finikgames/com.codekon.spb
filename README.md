# Приложение «Питер Live» (com.codekon.spb) — WebView для RuStore

Нативное Android WebView приложение для портала [mos77.ru/spb/](https://mos77.ru/spb/) («Куда сходить в Санкт-Петербурге: Афиша, События, Развлечения»), полностью подготовленное для публикации в **RuStore** с автоматической сборкой и релизной подписью через **GitHub Actions**.

---

## 📱 Характеристики приложения

| Параметр | Значение |
| :--- | :--- |
| **Название приложения** | Питер Live |
| **Package Name / Application ID** | `com.codekon.spb` |
| **Целевой URL** | `https://mos77.ru/spb/` |
| **Min SDK** | 24 (Android 7.0 Nougat) |
| **Target SDK / Compile SDK** | 34 (Android 14) |
| **Версия** | 1.0.0 (code: 1) |
| **Форматы сборки** | `.apk` (Release APK) + `.aab` (Android App Bundle) |

---

## 🔑 Данные релизной подписи (Keystore)

В проекте уже сгенерирован и настроен релизный ключ подписи:

- **Файл ключа:** `release.keystore` (в корне репозитория)
- **Пароль хранилища (Store Password):** `spb2024`
- **Алиас ключа (Key Alias):** `codekon`
- **Пароль ключа (Key Password):** `spb2024`
- **Срок действия:** 10 000 дней (~27 лет)
- **Схема подписи:** v1 + v2 (строго требуется RuStore)

> ⚠️ **Важно:** Сохраните этот файл ключа и пароли! Все последующие обновления приложения в RuStore должны быть подписаны **этим же самым ключом**.

---

## 🚀 Сборка через GitHub Actions

В репозитории уже настроен рабочий процесс `.github/workflows/build.yml`.

### Как запустить сборку:

1. Создайте репозиторий на [GitHub](https://github.com/new).
2. Загрузите файлы проекта в ваш GitHub-репозиторий:
   ```bash
   cd "/Users/admin/Desktop/spb_android_app"
   git init
   git add .
   git commit -m "Initial commit for Piter Live RuStore app"
   git branch -M main
   git remote add origin https://github.com/<ваш-логин>/<имя-репозитория>.git
   git push -u origin main
   ```
3. После пуша откройте вкладку **Actions** в репозитории на GitHub:
   - Сборка запустится автоматически.
   - По завершении в блоке **Artifacts** будут доступны для скачивания:
     - **`Piter-Live-Release-APK`** — готовый подписанный `.apk` файл для установки и тестирования.
     - **`Piter-Live-Release-AAB`** — готовый подписанный `.aab` файл (App Bundle) для публикации в RuStore.
     - **`Keystore-Backup`** — резервная копия ключа подписи.

---

## 📦 Публикация в RuStore

Пошаговая инструкция по публикации приложения в RuStore находится в файле [RUSTORE_PUBLISH_GUIDE.md](RUSTORE_PUBLISH_GUIDE.md).
Готовые тексты (название, краткое и полное описание) находятся в файле [RUSTORE_STORE_LISTING.txt](RUSTORE_STORE_LISTING.txt).
