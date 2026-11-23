# LAMBO Observatory

## О проекте / токене

LAMBO — токен в сети TON. В метаданных указан слоган «Wen $LAMBO ?\!». Канал проекта @lambospeak публикует тот же контракт и ссылается на чат @wen\_lambo\_ton и аккаунт X @LAMBOtokenTON. Конкретное назначение токена в метаданных не раскрыто.

Краткое описание по указанным первичным источникам.

Источники (проверены 2026-11-23):

- <https://tonapi.io/v2/jettons/EQDE1iPrP80L17RzkH3YluXsEcn5i-bPFfue259uMKKFE3h0>
- <https://t.me/lambospeak>
- <https://t.me/wen_lambo_ton>
- <https://lambo.tg>

Generated from https://github.com/Freebielife/TON-Observatory-Template.

Run python3 -m scripts.refresh_observatory; python3 build.py; python3 verify.py.
Publish index.html in TON Sites only after independent on-chain verification.
The repository contains a snapshot collected specifically for LAMBO. Section timestamps and incomplete-source errors remain visible; historical swap coverage accumulates across refreshes.
Only native TON swap pairs supported. Locks, staking and custom project NFT badges are configured through project.json and verified against TonAPI.
Configure your GitHub workflow scheduler before launch.

Foundation version: 1.3.0. Holders show 10, expandable to top 20.
`project.json` is the per-project specification. Contract/pool/precision changes require regenerating from the factory; do not reuse another token's snapshot.
Run `python3 build.py` for an atomic bundle and `build/report.json` size report.
No external fonts, scripts or images are needed to render the saved page. Fresh data checks and manual wallet lookups require network access.
Cloudflare dispatch registration and GitHub repository access remain separate deployment steps. No credentials go into HTML.

## Публикация и обновления

- Самостоятельный `index.html`: все изображения, стили и скрипты встроены. Загрузить этот файл в Resistance Tools / TON Storage.
- Источник новых снимков: `Freebielife/Lambo`, ветка `main`, `data/snapshot.json`; резерв — GitHub Contents API. Открытая страница проверяет новые данные каждые 5 минут.
- Workflow `update.yml` запускается после изменений исходников, вручную и по резервному расписанию GitHub каждые 30 минут (`:17/:47 UTC`). Фактические задержки GitHub возможны.
- Подключение к общему Cloudflare Worker пока не подтверждено: [настройки](docs/scheduler.md).
- Торговая история покрывает подтверждённые прямые обмены LAMBO/TON на STON.fi и DeDust. Основной пул для графика — STON.fi, выбран по наибольшей индексируемой ликвидности среди проверенных пулов.
- График оценивает капитализацию как цену сделки основного пула × текущее total supply. Это не капитализация свободного обращения; пропуски истории отмечаются.
- Метки OG, Fragment +888, четырёхзначные .ton и сжигания включены; проверки кошельков выполняются постепенно. Специальных меток других проектов нет.

Публикация в TON Storage и плановый запуск не подтверждены только наличием исходников или расписания.
