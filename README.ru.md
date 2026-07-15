# VLESS Tools

Одностраничный веб‑инструмент для работы с конфигами **VLESS**: массовая генерация по IP, извлечение адресов из списков и пакетный Morph. Установка не нужна — откройте HTML‑файл в браузере.

**Языки:** English · فارسی · Русский (переключатель в шапке; выбор сохраняется в `localStorage`).

---

## Возможности

### 1. Config Builder (Генератор)

- Вставьте базовую ссылку `vless://`; `@host:` заменяется на IP или CIDR.
- Вкладка **IP list**: ручной ввод, drag & drop, импорт файла (`.txt`, `.csv`, `.log`, `.json`).
- Вкладка **IP ranges**: пресеты CDN (Cloudflare, Fastly, Gcore) из [cdn-ip-ranges](https://github.com/vUnkname/cdn-ip-ranges); shuffle и лимит количества.
- Большие диапазоны CDN автоматически сэмплируются как `/24`.
- Разбиение на **части** с настраиваемым размером; копирование или скачивание по частям или целиком.
- Метрики: число IP, конфигов, частей.

### 2. IP Extractor (Извлечение IP)

- Разбор VLESS‑ссылок (или строк IP/CIDR).
- Фильтр **WS + TLS** (`type=ws`, `security=tls`).
- Извлечение **@address**, **sni=**, **host=**.
- Опциональное развёртывание CIDR в отдельные IP.
- Отчёт о дубликатах с копированием.

### 3. Config Morph

- Пакетное преобразование конфигов:
  - **Quick spoof:** перенаправление `@IP:Port` на локальный адрес (по умолчанию 127.0.0.1:40443).
  - **Advanced:** переключатели Address, SNI, HOST; ротация по списку доменов.

### Интерфейс

- Две темы: **CyberDeck** (киберпанк HUD) и **Simple** (минималистичная тёмная).
- Toast‑уведомления.
- Адаптивная вёрстка; RTL для персидского.

---

## Файлы

| Файл | Описание |
|------|----------|
| `index.html` | Стартовая страница GitHub Pages — выбор Cyber или Simple. |
| `vless-tools-all-in-one.html` | **Автономный** — CSS, JS, обе темы и встроенные CDN-данные (~270 KB). Полностью офлайн. |
| `vless-tools-cyber.html` | Тема CyberDeck; ссылка на Simple. Нужен `cyber-theme.css`. |
| `vless-tools-simple.html` | Простая тема; ссылка на Cyber. Нужен `simple-theme.css`. |
| `cyber-theme.css` | Стили CyberDeck. |
| `simple-theme.css` | Простые стили. |

---

## Быстрый старт

1. **GitHub Pages:** откройте `index.html` и выберите **Cyber** или **Simple**.
2. **Офлайн:** скачайте `vless-tools-all-in-one.html` и откройте в Chrome, Firefox или Edge.
3. **Пара тем:** держите `vless-tools-cyber.html` + `cyber-theme.css` (или simple + css) в одной папке.

> **All-in-one** содержит диапазоны Cloudflare, Fastly и Gcore — интернет не нужен. Версии cyber/simple загружают CDN-списки с GitHub.

---

## Переключение темы

| Вариант | Как |
|---------|-----|
| **All-in-one** | Кнопки **Simple / Cyber**; сохранение в `vless-ui-theme`. |
| **Cyber ↔ Simple** | Перекрёстные ссылки между HTML‑файлами. |

Язык сохраняется отдельно в `vless-lang`.

---

## Конфиденциальность

Обработка **локально в браузере**. На сервер ничего не отправляется, кроме опциональной загрузки CDN‑списков с GitHub.

---

## Другие языки

- [English (README.md)](README.md)
- [فارسی (README.fa.md)](README.fa.md)
