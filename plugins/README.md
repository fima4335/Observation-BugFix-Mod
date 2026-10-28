# Plugins (BepInEx / MelonLoader)

Здесь будут размещаться runtime-плагины для Observation.

## Планируемые плагины

### Observation.BugFix (BepInEx)

Цели:
- Автоматическое удаление cinematic letterboxing
- Принудительная установка нативного разрешения монитора
- Фикс сохранения настроек графики
- Корректная работа VSync
- Улучшение UI на ultrawide

### Почему BepInEx?

Игра использует **Unity 2017 (Mono)**. BepInEx 5.x отлично подходит для Mono-игр этого поколения.

## Как помочь

1. Установи BepInEx 5 в папку с игрой
2. Изучи Assembly-CSharp.dll (dnSpy / ILSpy)
3. Найди классы, отвечающие за:
   - Camera / Aspect ratio / Letterbox
   - Screenmanager / Resolution
   - Settings persistence
4. Создай Harmony-патчи

Pull Request'ы с рабочим кодом крайне приветствуются!
