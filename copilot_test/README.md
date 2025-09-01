# XRM Presentation Spec (ФТ) + Cursor Prompts

Этот пакет содержит **полное ФТ** для интерактивной HTML‑презентации XRM, стартовый контент и **готовые промты** для Cursor (IDE‑агент и GitHub‑агент).
Задумка — положить эту папку в репозиторий и попросить Cursor Agent собрать сайт в папку `/site` и открыть PR.

- Дата: 2025-08-31
- Язык: RU (с возможностью расширения на UK/EN)
- Модули: МК (Mass Campaigns), CJ (Customer Journeys), Templates

## Структура
```
/
├─ README.md
├─ docs/
│  └─ FT_presentation_XRM.md
├─ content/
│  ├─ 01_Intro.md
│  ├─ 02_Modules.md
│  ├─ 03_BusinessCanvas.md
│  └─ 04_Roadmap.md
└─ prompts/
   ├─ cursor_agent_mvp.txt
   └─ github_issue_cursor_mvp.md
```

## Быстрый старт (IDE‑агент)
1) Создай пустой репозиторий (локально/GitHub), скопируй сюда файлы.
2) Открой репозиторий в **Cursor**.
3) Открой `prompts/cursor_agent_mvp.txt` → **скопируй текст промта**.
4) Нажми **Agent** (иконка “ракеты”), вставь промт → **Run**.
5) Отвечай на уточнения (если будут). Проверь диффы → **Accept** → появятся коммиты/PR.

## Альтернатива (GitHub Issue, background‑агент)
1) Установи Cursor GitHub App (если доступно).
2) Создай Issue в репозитории и **вставь** содержимое `prompts/github_issue_cursor_mvp.md` (там есть `@cursor`).
3) Подожди PR → проверь результат → merge.

## Локальный просмотр
Если браузер блокирует загрузку Markdown с `file://`:
```
python3 -m http.server 8080 -d site
# затем открой http://localhost:8080
```

## Что сделает агент
- Создаст `/site` с `index.html`, `styles.css`, `router.js`, механизмом подгрузки Markdown из `/content`.
- Добавит переключатель темы (light/dark), анимации, стили для печати (PDF).
- Предложит GitHub Actions workflow для GitHub Pages.
