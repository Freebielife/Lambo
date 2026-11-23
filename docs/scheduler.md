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

Рабочий реестр Cloudflare в этой сессии недоступен; эта запись только подготовлена. Подключение Cloudflare и плановый запуск не подтверждены. Резервное расписание GitHub не является доказательством работы Cloudflare.
