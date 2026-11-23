# Обновление LAMBO

Workflow: `.github/workflows/update.yml`.
Резервное расписание GitHub Actions: `17,47 * * * *` (UTC), каждые 30 минут; фактические запуски могут задерживаться GitHub. Также поддерживаются workflow_dispatch и запуск после изменений исходников.

Для существующего общего Cloudflare Worker `freebie-observatory-runner` нужна отдельная запись в полном рабочем реестре:

```js
Object.freeze({id: 'lambo', owner: 'Freebielife', repo: 'Lambo',
  workflow: 'update.yml', ref: 'main', everyMinutes: 30,
  phaseMinutes: 10, enabled: true})
```

Сохранить все остальные записи рабочего реестра. GitHub-токен Worker должен иметь доступ к Freebielife/Lambo и Actions: write. Секреты в репозиторий не добавлять.

LAMBO добавлен в действующий исходный реестр `Freebielife/Ludoman/cloudflare/observatory-runner/src/projects.mjs`, коммит `64ce404cca829b6eaad367de601598495c07fce4`. Остальные проекты сохранены; 17 тестов планировщика проходят.

Первый запуск GitHub Actions после сохранения исходников успешно собрал и опубликовал снимок: https://github.com/Freebielife/Lambo/actions/runs/45266026055 . Это был push-запуск, не плановый workflow_dispatch.

Развёртывание Cloudflare, доступ его токена к Lambo и плановый запуск ещё не подтверждены. Резервное расписание GitHub не является доказательством работы Cloudflare.
