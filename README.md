# Каталог модулей MajorDoMo v2

Единая точка входа для модулей, подготовленных mambursoft и опубликованных отдельно от upstream-репозиториев.

## Принцип

- **v2 не заменяет оригинал автоматически** — ставьте вместо исходного модуля, не вместе с ним.
- Пакеты публикуются в маркете Connect с суффиксом **v2**.
- Архивы собираются автоматически через GitHub Actions при пуше тега `v*`.
- Второй пилот: @sergejey (запрошения на репозитории отправлены).

## Модули

| Модуль | Источник | Назначение |
|---|---|---|
| MQTT v2 | https://github.com/mambursoft/majordomo-mqtt-v2 | MQTT-мост: валидация топиков, адаптивная форма, локализация en/ru/uk |
| Tuya v2 | https://github.com/mambursoft/majordomo-tuya-v2 | Tuya Cloud/Local: чистый PHP вместо exec, скрытый пароль, адаптивный UI |
| Xiaomi miIO v2 | https://github.com/mambursoft/majordomo-xiaomimiio-v2 | Xiaomi miIO: облачный коннектор на PHP, проверка прав AJAX, блокировки id.json |
| Google Location v2 | https://github.com/mambursoft/majordomo-google-location-v2 | Геолокация через Google Family Link/Location Sharing, GPS Tracker, карта и мануал |
| Icons | https://github.com/mambursoft/majordomo-icons | Локальные иконки без CDN, совместимость с glyphicon |
| Solar Planner | https://github.com/mambursoft/majordomo-solarPlanner | Планировщик солнечной генерации и ночного заряда батарей |
| TabCalorie | https://github.com/mambursoft/majordomo_TabCalorie | Локальный контроль углеводов, en/ru/uk |

| Meter Upload v2 | https://github.com/mambursoft/majordomo-meter-upload-v2 | Универсальная отправка показаний счётчиков: провайдеры ТЭСК/ТОСК/Saures/«Мой газ» и произвольный endpoint |
## Релизы v2.0.0

- [MQTT v2](https://github.com/mambursoft/majordomo-mqtt-v2/releases/tag/v2.0.0) — архивы `majordomo-mqtt-v2-v2.0.0.tar.gz` и `.zip`
- [Tuya v2](https://github.com/mambursoft/majordomo-tuya-v2/releases/tag/v2.0.0) — архивы `majordomo-tuya-v2-v2.0.0.tar.gz` и `.zip`
- [Xiaomi miIO v2](https://github.com/mambursoft/majordomo-xiaomimiio-v2/releases/tag/v2.0.0) — архивы `majordomo-xiaomimiio-v2-v2.0.0.tar.gz` и `.zip`
- [Google Location v2](https://github.com/mambursoft/majordomo-google-location-v2/releases/tag/v2.0.0) — архивы `majordomo-google-location-v2-v2.0.0.tar.gz` и `.zip`

Архивы собираются автоматически через GitHub Actions при пуше тега `v*`.
- Meter Upload v2: https://github.com/mambursoft/majordomo-meter-upload-v2/releases/tag/v2.0.0
## Установка

1. Скачайте `tar.gz` из раздела Releases нужного репозитория (или используйте URL пакета в маркете Connect).
2. Распакуйте архив в корень MajorDoMo.
3. Откройте «Настройки» в панели управления.
4. Включите модуль и ознакомьтесь с мануалом в его интерфейсе.

## Мануалы

- Общий мануал по каждому модулю: `docs/MANUAL.md` в репозитории модуля.
- Пункт «Manual» доступен в админке соответствующего модуля.
- Вопросы и предложения: Issues в репозитории модуля или https://github.com/sergejey/majordomo/issues

## Обратная связь

Если нашли проблему — открывайте issue в конкретном репозитории. Пожалуйста, указывайте версию PHP, версию MajorDoMo и шаги воспроизведения.