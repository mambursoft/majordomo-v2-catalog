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

| Meter Upload v2 | https://github.com/mambursoft/majordomo-meter-upload-v2 | Универсальная отправка показаний: ТЭСК/ТОСК/Saures/«Мой газ», Київенерго/Київгаз/Укргаз/Львівгаз, фізособи та юрособи, ручний режим для Ясно/КиївВодоканал/Київтеплоенерго/ДТЕК, офлайн-очередь |
| Presence v2 | https://github.com/mambursoft/majordomo-presence-v2 | Локальное определение присутствия по BLE-меткам через MQTT; адаптировано под Europe/Kyiv и работу без интернета |
| Ukraine Alarm v2 | https://github.com/mambursoft/majordomo-ukraine_alarm-v2 | Воздушные тревоги по регионам |
| Nova Poshta v2 | https://github.com/mambursoft/majordomo-nova_poshta-v2 | Статус отправлений |
| Smart MAIC v2 | https://github.com/mambursoft/majordomo-smart_maic-v2 | Локальный счётчик энергии |
| Check Weather v2 | https://github.com/mambursoft/majordomo-check_weather-v2 | Советы по погоде для прогулок |
| Frigate Events v2 | https://github.com/mambursoft/majordomo-frigate_events-v2 | События камер |
| Tailscale Status v2 | https://github.com/mambursoft/majordomo-tailscale_status-v2 | Состояние устройств VPN |
| Cloudflared Status v2 | https://github.com/mambursoft/majordomo-cloudflared_status-v2 | Здоровье туннеля |
| Vaultwarden Status v2 | https://github.com/mambursoft/majordomo-vaultwarden_status-v2 | Доступность хранилища паролей |
| Android TV Remote v2 | https://github.com/mambursoft/majordomo-android_tv_remote-v2 | Локальное управление TV |
| Supervisor Status v2 | https://github.com/mambursoft/majordomo-supervisor_status-v2 | Состояние локального API |
| ESPHome Bridge v2 | https://github.com/mambursoft/majordomo-esphome_bridge-v2 | Локальный мост устройств ESPHome |
| Zigbee2MQTT Status v2 | https://github.com/mambursoft/majordomo-zigbee2mqtt_status-v2 | Состояние координатора Zigbee |
| Node-RED Status v2 | https://github.com/mambursoft/majordomo-nodered_status-v2 | Доступность редактора потоков |
| Piper TTS v2 | https://github.com/mambursoft/majordomo-piper_tts-v2 | Локальный синтез речи |
| Whisper STT v2 | https://github.com/mambursoft/majordomo-whisper_stt-v2 | Локальное распознавание речи |
| AdGuard Home Status v2 | https://github.com/mambursoft/majordomo-adguard_home-v2 | Здоровье домашнего DNS |
| Samba Backup Status v2 | https://github.com/mambursoft/majordomo-samba_backup-v2 | Локальные резервные копии |
| Matter Bridge Status v2 | https://github.com/mambursoft/majordomo-matter_bridge-v2 | Локальный контроллер Matter |
| OpenWakeWord Status v2 | https://github.com/mambursoft/majordomo-openwakeword-v2 | Локальные ключевые фразы |
| Adaptive Lighting v2 | https://github.com/mambursoft/majordomo-adaptive_lighting-v2 | Освещение по положению солнца |
## Релизы v2.0.0

- [MQTT v2](https://github.com/mambursoft/majordomo-mqtt-v2/releases/tag/v2.0.0) — архивы `majordomo-mqtt-v2-v2.0.0.tar.gz` и `.zip`
- [Tuya v2](https://github.com/mambursoft/majordomo-tuya-v2/releases/tag/v2.0.0) — архивы `majordomo-tuya-v2-v2.0.0.tar.gz` и `.zip`
- [Xiaomi miIO v2](https://github.com/mambursoft/majordomo-xiaomimiio-v2/releases/tag/v2.0.0) — архивы `majordomo-xiaomimiio-v2-v2.0.0.tar.gz` и `.zip`
- [Google Location v2](https://github.com/mambursoft/majordomo-google-location-v2/releases/tag/v2.0.0) — архивы `majordomo-google-location-v2-v2.0.0.tar.gz` и `.zip`

Архивы собираются автоматически через GitHub Actions при пуше тега `v*`.
- Meter Upload v2: https://github.com/mambursoft/majordomo-meter-upload-v2/releases/tag/v2.3.0
- Presence v2: https://github.com/mambursoft/majordomo-presence-v2/releases/tag/v2.1.0
- Ukraine Alarm v2: https://github.com/mambursoft/majordomo-ukraine_alarm-v2/releases/tag/v1.0.0
- Nova Poshta v2: https://github.com/mambursoft/majordomo-nova_poshta-v2/releases/tag/v1.0.0
- Smart MAIC v2: https://github.com/mambursoft/majordomo-smart_maic-v2/releases/tag/v1.0.0
- Check Weather v2: https://github.com/mambursoft/majordomo-check_weather-v2/releases/tag/v1.0.0
- Frigate Events v2: https://github.com/mambursoft/majordomo-frigate_events-v2/releases/tag/v1.0.0
- Tailscale Status v2: https://github.com/mambursoft/majordomo-tailscale_status-v2/releases/tag/v1.0.0
- Cloudflared Status v2: https://github.com/mambursoft/majordomo-cloudflared_status-v2/releases/tag/v1.0.0
- Vaultwarden Status v2: https://github.com/mambursoft/majordomo-vaultwarden_status-v2/releases/tag/v1.0.0
- Android TV Remote v2: https://github.com/mambursoft/majordomo-android_tv_remote-v2/releases/tag/v1.0.0
- Supervisor Status v2: https://github.com/mambursoft/majordomo-supervisor_status-v2/releases/tag/v1.0.0
- ESPHome Bridge v2: https://github.com/mambursoft/majordomo-esphome_bridge-v2/releases/tag/v1.0.0
- Zigbee2MQTT Status v2: https://github.com/mambursoft/majordomo-zigbee2mqtt_status-v2/releases/tag/v1.0.0
- Node-RED Status v2: https://github.com/mambursoft/majordomo-nodered_status-v2/releases/tag/v1.0.0
- Piper TTS v2: https://github.com/mambursoft/majordomo-piper_tts-v2/releases/tag/v1.0.0
- Whisper STT v2: https://github.com/mambursoft/majordomo-whisper_stt-v2/releases/tag/v1.0.0
- AdGuard Home Status v2: https://github.com/mambursoft/majordomo-adguard_home-v2/releases/tag/v1.0.0
- Samba Backup Status v2: https://github.com/mambursoft/majordomo-samba_backup-v2/releases/tag/v1.0.0
- Matter Bridge Status v2: https://github.com/mambursoft/majordomo-matter_bridge-v2/releases/tag/v1.0.0
- OpenWakeWord Status v2: https://github.com/mambursoft/majordomo-openwakeword-v2/releases/tag/v1.0.0
- Adaptive Lighting v2: https://github.com/mambursoft/majordomo-adaptive_lighting-v2/releases/tag/v1.0.0
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