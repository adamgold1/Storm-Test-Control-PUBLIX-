# Storm-Test-Control-PUBLIX-
# Storm Test Control

Storm Test Control is a local testing control room for VS Code.

It runs your checks inside a disposable shadow copy of the workspace, streams live progress into a premium dashboard, writes reports, and keeps the original project untouched.

---

## English

### What It Is

Storm Test Control is built for one simple idea:

**scan, clone, inject, test, report, and clean up without touching the real project.**

It is designed for people who want a strong local testing workflow with live control, clear visibility, and zero manual markup inside the original codebase.

### Core Product Capabilities

- **Shadow-copy execution**
  Every run happens inside an isolated clone of the workspace.

- **Non-destructive selector injection**
  Test markers are injected into the cloned copy only, never into the original project.

- **Live control room inside VS Code**
  The extension provides a full dashboard with run state, pipeline progress, operator hints, live test feed, timeline, console output, and result mix.

- **Multiple suite modes**
  Run:
  - `Smoke`
  - `Functional`
  - `E2E`
  - `UI`
  - `Full Suite`

- **Real-time streaming**
  Progress and test results appear while the run is still active.

- **Safe runtime controls**
  During a run, `Stop Tests` stays available while other conflicting actions are temporarily locked.

- **Cancellation that behaves correctly**
  A cancelled run is treated as **cancelled**, not as a fake failure.

- **Automatic backend supervision**
  The system checks backend health, restarts when needed, and protects the run lifecycle from stale state.

- **Hard cleanup policy**
  Managed processes, sockets, and busy ports are cleaned up on stop, restart, shutdown, and next startup.

- **Project-scoped ignore rules**
  Each project gets its own `.storm-test.yaml` file with a large default blacklist for generated, vendor, and tool-owned files.

- **Editable ignore configuration**
  Ignore rules can be opened, edited, and saved directly from the UI through **Edit Ignore Rules**.

- **Saved project behavior**
  Once ignore rules are saved, every next run follows them automatically.

- **Reports**
  Storm Test Control writes report artifacts to `.storm-test-reports/` so you can inspect the run after completion.

- **Project snapshot**
  The dashboard shows supported files, workspace size, languages, frameworks, ignore config path, ignore rule count, entry pages, Python tests, and testable targets.

### What It Helps You Avoid

- Manual `data-test-id` annotation in the real project
- Polluting the original workspace with test-only edits
- Confusing “cancelled = failed” UX
- Zombie processes and stale backend ports
- False positives from generated folders, browser binaries, local tooling, and report artifacts

### Typical Flow

1. Open a workspace in VS Code.
2. Open **Storm Test Control**.
3. Review the project snapshot.
4. Adjust `.storm-test.yaml` if needed through **Edit Ignore Rules**.
5. Launch a suite.
6. Watch the run stream live.
7. Stop, restart, or inspect the HTML report when needed.

### Product Direction

Storm Test Control is not meant to feel like a passive test runner.

It is meant to feel like a **local mission control center** for workspace validation:

- visible
- interruptible
- isolated
- recoverable
- operator-friendly

---

## Русский

### Что Это Такое

Storm Test Control построен вокруг простой идеи:

**сканировать, клонировать, внедрять, тестировать, формировать отчёты и очищать окружение, не трогая реальный проект.**

Это локальный центр управления тестированием внутри VS Code для тех, кому нужен живой контроль, наглядность и аккуратная работа без правок исходного проекта.

### Ключевой Функционал

- **Теневое выполнение**
  Каждый запуск идёт внутри изолированной shadow-copy рабочей папки.

- **Неразрушающая инъекция селекторов**
  Тестовые маркеры внедряются только в копию проекта, а не в оригинальные файлы.

- **Живой control room прямо в VS Code**
  В расширении есть полноценная панель с состоянием запуска, прогрессом пайплайна, operator hints, live test feed, timeline, console и визуальной сводкой результатов.

- **Несколько режимов запуска**
  Поддерживаются:
  - `Smoke`
  - `Functional`
  - `E2E`
  - `UI`
  - `Full Suite`

- **Потоковая выдача результатов**
  События и результаты приходят в интерфейс в реальном времени, пока запуск ещё продолжается.

- **Безопасные runtime-кнопки**
  Во время выполнения `Stop Tests` остаётся доступной, а конфликтующие действия временно блокируются.

- **Корректная отмена**
  Остановленный запуск показывается как **cancelled**, а не как ложный `failed`.

- **Автоматический контроль backend**
  Система проверяет здоровье backend, умеет корректно перезапускаться и защищает lifecycle от зависшего состояния.

- **Жёсткая политика очистки**
  Управляемые процессы, сокеты и занятые порты зачищаются при stop, restart, shutdown и при следующем старте.

- **Проектный ignore-конфиг**
  Для каждого проекта создаётся свой `.storm-test.yaml` с большим стартовым blacklist для generated, vendor и tool-owned файлов.

- **Редактирование ignore-правил из интерфейса**
  Ignore rules можно открыть, изменить и сохранить прямо из UI через **Edit Ignore Rules**.

- **Сохранение правил на будущее**
  После сохранения Storm Test Control автоматически использует эти правила во всех следующих запусках.

- **Отчёты**
  После завершения запуска сохраняются артефакты в `.storm-test-reports/`.

- **Снимок проекта**
  Панель показывает количество поддерживаемых файлов, размер workspace, языки, найденные framework-маркеры, путь к ignore-конфигу, количество ignore-правил, HTML entry pages, Python tests и testable targets.

### Что Это Убирает Из Рабочего Процесса

- Ручную разметку `data-test-id` в реальном проекте
- Загрязнение исходников тестовыми правками
- Плохой UX, где отмена выглядит как ошибка
- Зомби-процессы и зависшие backend-порты
- Ложные падения на generated-папках, browser binaries, локальных инструментах и старых report-файлах

### Типовой Сценарий

1. Открываешь проект в VS Code.
2. Открываешь **Storm Test Control**.
3. Смотришь project snapshot.
4. При необходимости редактируешь `.storm-test.yaml` через **Edit Ignore Rules**.
5. Запускаешь нужный suite.
6. Смотришь live pipeline прямо в панели.
7. Останавливаешь, перезапускаешь backend или открываешь HTML report, когда это нужно.

### Продуктовая Идея

Storm Test Control не должен ощущаться как обычный тихий тест-раннер.

Он должен ощущаться как **локальный центр управления проверками проекта**:

- наглядный
- управляемый
- изолированный
- восстанавливаемый
- удобный для оператора

---

## Name

**Storm Test Control**

If you want, the next step is to also make the repository presentation layer match this README:

- a cleaner project description
- release notes
- screenshots/gifs section
- a public roadmap
- a sharper GitHub profile presentation
