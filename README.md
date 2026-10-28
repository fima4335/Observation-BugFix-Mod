# Observation BugFix Mod

**Сообщественный мод / патч для исправления багов в игре Observation (No Code Studio / Devolver Digital)**

[English below](#english)

## О проекте

Игра *Observation* (2019) — отличный sci-fi puzzle от No Code, но у неё есть несколько давних проблем:

- Чёрные полосы (letterboxing) на всех разрешениях
- Ограничение списка разрешений (особенно после патча 1.17)
- Проблемы с ultrawide / 21:9 / 32:9
- Резолюция сбрасывается / не сохраняется
- Краши при запуске, особенно с контроллерами / NVIDIA Overlay
- Перевернутый VSync
- Обрезанные подсказки управления на широких экранах

Этот репозиторий собирает **известные рабочие фиксы** и служит основой для более продвинутого мода (BepInEx / MelonLoader).

## Известные и рабочие фиксы

### 1. Удаление чёрных полос (Black Bars Removal)
Самый популярный фикс от Rose (PCGamingWiki):
- Распаковать файлы рядом с `Observation.exe`
- Ссылки: [PCGamingWiki](https://community.pcgamingwiki.com/files/file/1900-observation-black-bars-removal/) | [VGTimes](https://vgtimes.com/games/observation/files/22484-removing-black-stripes.html)

### 2. Ultrawide / снятие лимита разрешений
Патчер от Rose:
- [Observation ultrawide workaround](https://community.pcgamingwiki.com/files/file/1960-observation-ultrawide-workaround/)
- После патча выбирай любое 16:9 выше своего нативного — игра применит реальное разрешение монитора.

### 3. Резолюция сбрасывается
Через реестр (Windows):
```
HKEY_CURRENT_USER\Software\No Code Studio\Observation
```
- `Dropdown_Resolution` = 14 (decimal)
- `Screenmanager Resolution Width` / `Height` = твоё разрешение

Рекомендуется экспортировать ключ в `.reg` файл и применять перед запуском.

### 4. Краши при запуске
- Запуск в режиме совместимости Windows 8
- Отключить NVIDIA Overlay / GeForce Experience
- Отключить контроллер или настроить через Steam Input
- Launch option: `-window-mode exclusive`
- Override High DPI scaling → Application

### 5. VSync перевернут
В настройках игры:
- Включить VSync = выключить
- Выключить VSync = включить

## Структура репозитория

```
Observation-BugFix-Mod/
├── README.md
├── docs/
│   └── known-issues.md
├── tools/
│   └── set-resolution.reg.example
├── plugins/          # будущие BepInEx/MelonLoader плагины
└── LICENSE
```

## Планы

- [ ] BepInEx-плагин для автоматического удаления letterboxing
- [ ] Принудительная установка нативного разрешения
- [ ] Фикс сохранения настроек
- [ ] Поддержка ultrawide без ручного выбора
- [ ] Исправление UI на широких экранах

## Требования

- Игра Observation (Steam / Epic / GOG)
- Windows (основная платформа)
- Для будущих плагинов: BepInEx 5.x (Unity Mono)

## Вклад

Pull Request'ы и Issues приветствуются.  
Если у тебя есть рабочий фикс — кидай!

---

## English

Community bugfix project / mod for **Observation** by No Code.

### Known issues fixed by community tools:
- Cinematic black bars (letterboxing)
- Hardcoded resolution list after v1.17
- Ultrawide support
- Resolution not saving
- Startup crashes (overlays, controllers, DPI)
- Inverted VSync

This repository collects proven workarounds and is intended as a foundation for a proper runtime mod (BepInEx preferred, since the game uses Unity 2017 Mono).

### Quick fixes
See Russian section above for detailed steps and links to existing patches by Rose on PCGamingWiki.

### License
MIT — free to use, modify and redistribute.

---

**Сделано сообществом для сообщества.**  
Enjoy the game without the jank.
