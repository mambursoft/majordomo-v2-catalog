# Каталог модулей MajorDoMo v2

Единая точка входа для модулей, подготовленных mambursoft и опубликованных отдельно от upstream-репозиториев. Каталог является документацией и не устанавливается как отдельный модуль.

## Принцип

- **v2 не заменяет оригинал автоматически** — ставьте вместо исходного модуля, не вместе с ним.
- Пакеты публикуются в маркете Connect с суффиксом **v2**.
- Архивы собираются автоматически через GitHub Actions при пуше тега `v*`; для части репозиториев их собирает workflow `build-package.yml`.
- В таблицах указан последний опубликованный тег. Прочерк означает, что готового релиза нет — берите исходники репозитория.
- Второй пилот: @sergejey (запрошения на репозитории отправлены).

## Состав каталога

Всего 46 пакетов. Таблицы сгруппированы по решаемой задаче; каждая группа содержит собственную шапку, чтобы разметка не ломалась при просмотре на GitHub.

### Шлюзы и базовые сервисы

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| MQTT v2 | https://github.com/mambursoft/majordomo-mqtt-v2 | MQTT-мост: валидация топиков, адаптивная форма, локализация en/ru/uk | `v2.4.0` |
| Tuya v2 | https://github.com/mambursoft/majordomo-tuya-v2 | Tuya Cloud/Local: чистый PHP вместо exec, скрытый пароль, адаптивный UI | `v2.0.0` |
| Xiaomi miIO v2 | https://github.com/mambursoft/majordomo-xiaomimiio-v2 | Xiaomi miIO: PHP-коннектор вместо exec, проверка прав AJAX, блокировки `id.json` | `v2.0.0` |
| Xiaomi Miot Auto v2 | https://github.com/mambursoft/majordomo-xiaomi_miot_auto-v2 | Локальное управление устройствами Xiaomi через miot-мост | `v1.0.0` |
| Google Location v2 | https://github.com/mambursoft/majordomo-google-location-v2 | Геолокация через Family Link и Location Sharing, передача в GPS Tracker, карта и мануал | `v2.0.0` |
| Presence v2 | https://github.com/mambursoft/majordomo-presence-v2 | Локальное определение присутствия по BLE-меткам через MQTT, Europe/Kyiv, без интернета | `v2.2.0` |
| ESPHome Bridge v2 | https://github.com/mambursoft/majordomo-esphome_bridge-v2 | Локальный мост устройств ESPHome по HTTP или MQTT | `v1.0.0` |

### Устройства и мультимедиа

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| Zigbee2MQTT Status v2 | https://github.com/mambursoft/majordomo-zigbee2mqtt_status-v2 | Состояние координатора и устройств Zigbee без облака | `v1.0.0` |
| Z-Wave JS UI v2 | https://github.com/mambursoft/majordomo-zwave_js_ui-v2 | Состояние контроллера Z-Wave | `v1.0.0` |
| MegaD Bridge v2 | https://github.com/mambursoft/majordomo-megad_bridge-v2 | Мост контроллера MegaD, локальное управление | `v1.0.0` |
| ONVIF Bridge v2 | https://github.com/mambursoft/majordomo-onvif_bridge-v2 | ONVIF-профили, RTSP, события движения и PTZ-действия | `v1.0.0` |
| SSDP Discovery v2 | https://github.com/mambursoft/majordomo-ssdp_discovery-v2 | Обнаружение устройств по SSDP в локальной сети | `v1.0.0` |
| Google Cast v2 | https://github.com/mambursoft/majordomo-google_cast-v2 | Локальная отправка медиа на устройства Google Cast | `v1.0.0` |
| openHASP Bridge v2 | https://github.com/mambursoft/majordomo-openhasp_bridge-v2 | Мост панелей openHASP через MQTT | `v1.0.0` |
| Shelly Gen2 v2 | https://github.com/mambursoft/majordomo-shelly_gen2-v2 | Показания и состояние устройств Shelly Gen2 | `v1.0.0` |
| Tasmota Status v2 | https://github.com/mambursoft/majordomo-tasmota_status-v2 | Состояние устройств Tasmota | `v1.0.0` |
| Android TV Remote v2 | https://github.com/mambursoft/majordomo-android_tv_remote-v2 | Локальное управление Android TV через HTTP-мост | `v1.0.0` |
| LG webOS TV v2 | https://github.com/mambursoft/majordomo-lg_webos_tv-v2 | Локальный мост телевизоров LG webOS | `v1.0.0` |
| Samsung TV v2 | https://github.com/mambursoft/majordomo-samsung_tv-v2 | Локальный мост телевизоров Samsung | `v1.0.0` |
| Kodi Media v2 | https://github.com/mambursoft/majordomo-kodi_media-v2 | Управление Kodi через JSON-RPC | `v1.0.0` |
| Adaptive Lighting v2 | https://github.com/mambursoft/majordomo-adaptive_lighting-v2 | Яркость и цветовая температура освещения по положению солнца | `v1.0.0` |
| Matter Bridge Status v2 | https://github.com/mambursoft/majordomo-matter_bridge-v2 | Состояние локального контроллера Matter и устройств | `v1.0.0` |

### Энергия, вода, погода

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| Solar Planner | https://github.com/mambursoft/majordomo-solarPlanner | Планировщик генерации, прогноз нагрузки, расчёт TargetSocAt07 и расписание Deye Time of Use | — |
| Smart MAIC v2 | https://github.com/mambursoft/majordomo-smart_maic-v2 | Локальный учёт энергии WiFi-счётчика Smart MAIC | `v1.0.0` |
| Meter Upload v2 | https://github.com/mambursoft/majordomo-meter-upload-v2 | Отправка показаний: ТЭСК/ТОСК/Saures/«Мой газ», Киевэнерго/Киевгаз/Укргаз/Львовгаз, физ- и юрлица, офлайн-очередь | `v2.3.0` |
| Check Weather v2 | https://github.com/mambursoft/majordomo-check_weather-v2 | Советы по дождю, прогулкам и поездкам на велосипеде | `v1.0.0` |

### Сеть, безопасность, резервные копии

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| Tailscale Status v2 | https://github.com/mambursoft/majordomo-tailscale_status-v2 | Состояние устройств Tailscale через официальный API | `v1.0.0` |
| Cloudflared Status v2 | https://github.com/mambursoft/majordomo-cloudflared_status-v2 | Здоровье локального туннеля по metrics endpoint | `v1.0.0` |
| Vaultwarden Status v2 | https://github.com/mambursoft/majordomo-vaultwarden_status-v2 | Доступность локального хранилища паролей | `v1.0.0` |
| AdGuard Home Status v2 | https://github.com/mambursoft/majordomo-adguard_home-v2 | Здоровье домашнего DNS-фильтра | `v1.0.0` |
| Samba Backup Status v2 | https://github.com/mambursoft/majordomo-samba_backup-v2 | Проверка локальных резервных копий через Samba bridge | `v1.0.0` |
| Supervisor Status v2 | https://github.com/mambursoft/majordomo-supervisor_status-v2 | Состояние локального API по токену | `v1.0.0` |
| Node-RED Status v2 | https://github.com/mambursoft/majordomo-nodered_status-v2 | Доступность локального редактора потоков | `v1.0.0` |
| Frigate Events v2 | https://github.com/mambursoft/majordomo-frigate_events-v2 | Последние события камер и статус камер без облака | `v1.0.0` |

### Голос и речь

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| Piper TTS v2 | https://github.com/mambursoft/majordomo-piper_tts-v2 | Локальный синтез речи с украинскими и русскими голосами | `v1.0.0` |
| Whisper STT v2 | https://github.com/mambursoft/majordomo-whisper_stt-v2 | Локальное распознавание речи через Wyoming Whisper | `v1.0.0` |
| OpenWakeWord Status v2 | https://github.com/mambursoft/majordomo-openwakeword-v2 | Обнаружение ключевых фраз без облачных сервисов | `v1.0.0` |

### Украина и здоровье

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| Ukraine Alarm v2 | https://github.com/mambursoft/majordomo-ukraine_alarm-v2 | Воздушные тревоги по регионам через публичный API | `v1.0.0` |
| Nova Poshta v2 | https://github.com/mambursoft/majordomo-nova_poshta-v2 | Статус отправлений через официальный API | `v1.0.0` |
| Ukrposhta Tracking v2 | https://github.com/mambursoft/majordomo-ukrposhta_tracking-v2 | Статус отправлений Укрпочты | `v1.0.0` |
| SaveEcoBot Air Quality v2 | https://github.com/mambursoft/majordomo-saveecobot_air-v2 | Качество воздуха в Украине | `v1.0.0` |
| CGM / Nightscout v2 | https://github.com/mambursoft/majordomo-cgm-v2 | Уровень глюкозы из Nightscout/Juggluco, тревоги и объекты MajorDoMo | `v1.0.0` |
| TabCalorie | https://github.com/mambursoft/majordomo_TabCalorie | Локальный контроль углеводов, шесть приёмов пищи, справочник ГИ, CSV | `v1.4.2` |

### Инструменты и утилиты

| Модуль | Источник | Назначение | Релиз |
|---|---|---|---|
| Icons | https://github.com/mambursoft/majordomo-icons | Локальные иконки без CDN, совместимость с `glyphicon`, синхронизация с ядром | — |
| qBittorrent Status v2 | https://github.com/mambursoft/majordomo-qbittorrent_status-v2 | Состояние WebUI клиента qBittorrent | `v1.0.0` |
| ESP32 ↔ Drazice SMART | https://github.com/mambursoft/majordomo-ESP32-Drazice | Мониторинг и безопасное управление бойлером через Wi-Fi → ESP32 → BLE | `v1.17.1` |

## Направления интеграций

В репозитории есть фактический анализ восьми направлений: [Tuya, Xiaomi, ONVIF, Zigbee, SSDP, Google Cast, openHASP, MegaD](doc/20261126_SMART_HOME_INTEGRATIONS_GAPS.md). Для каждого направления сравнены реализация Home Assistant, OpenHAB и текущее состояние MajorDoMo, сформулированы требования к модулю и решено, что улучшать, а что создавать заново.

Пакеты ONVIF Bridge v2, SSDP Discovery v2, Google Cast v2, openHASP Bridge v2 и MegaD Bridge v2 уже опубликованы. Для Tuya v2 и Xiaomi (miIO и Miot Auto) в плане — явное разделение облачного и локального режимов, поля `device_id`, `local_key`, `did`, `model` и маскирование токенов.

## Релизы

| Модуль | Версия | Ссылка |
|---|---|---|
| MQTT v2 | `v2.4.0` | https://github.com/mambursoft/majordomo-mqtt-v2/releases/tag/v2.4.0 |
| Meter Upload v2 | `v2.3.0` | https://github.com/mambursoft/majordomo-meter-upload-v2/releases/tag/v2.3.0 |
| Presence v2 | `v2.2.0` | https://github.com/mambursoft/majordomo-presence-v2/releases/tag/v2.2.0 |
| Tuya v2 | `v2.0.0` | https://github.com/mambursoft/majordomo-tuya-v2/releases/tag/v2.0.0 |
| Xiaomi miIO v2 | `v2.0.0` | https://github.com/mambursoft/majordomo-xiaomimiio-v2/releases/tag/v2.0.0 |
| Google Location v2 | `v2.0.0` | https://github.com/mambursoft/majordomo-google-location-v2/releases/tag/v2.0.0 |
| CGM / Nightscout v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-cgm-v2/releases/tag/v1.0.0 |
| ESP32 ↔ Drazice SMART | `v1.17.1` | https://github.com/mambursoft/majordomo-ESP32-Drazice/releases/tag/v1.17.1 |
| TabCalorie | `v1.4.2` | https://github.com/mambursoft/majordomo_TabCalorie/releases/tag/v1.4.2 |
| Xiaomi Miot Auto v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-xiaomi_miot_auto-v2/releases/tag/v1.0.0 |
| MegaD Bridge v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-megad_bridge-v2/releases/tag/v1.0.0 |
| ONVIF Bridge v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-onvif_bridge-v2/releases/tag/v1.0.0 |
| SSDP Discovery v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-ssdp_discovery-v2/releases/tag/v1.0.0 |
| Google Cast v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-google_cast-v2/releases/tag/v1.0.0 |
| openHASP Bridge v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-openhasp_bridge-v2/releases/tag/v1.0.0 |
| ESPHome Bridge v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-esphome_bridge-v2/releases/tag/v1.0.0 |
| Zigbee2MQTT Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-zigbee2mqtt_status-v2/releases/tag/v1.0.0 |
| Z-Wave JS UI v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-zwave_js_ui-v2/releases/tag/v1.0.0 |
| Shelly Gen2 v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-shelly_gen2-v2/releases/tag/v1.0.0 |
| Tasmota Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-tasmota_status-v2/releases/tag/v1.0.0 |
| Android TV Remote v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-android_tv_remote-v2/releases/tag/v1.0.0 |
| LG webOS TV v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-lg_webos_tv-v2/releases/tag/v1.0.0 |
| Samsung TV v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-samsung_tv-v2/releases/tag/v1.0.0 |
| Kodi Media v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-kodi_media-v2/releases/tag/v1.0.0 |
| Adaptive Lighting v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-adaptive_lighting-v2/releases/tag/v1.0.0 |
| Matter Bridge Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-matter_bridge-v2/releases/tag/v1.0.0 |
| Smart MAIC v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-smart_maic-v2/releases/tag/v1.0.0 |
| Check Weather v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-check_weather-v2/releases/tag/v1.0.0 |
| Tailscale Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-tailscale_status-v2/releases/tag/v1.0.0 |
| Cloudflared Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-cloudflared_status-v2/releases/tag/v1.0.0 |
| Vaultwarden Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-vaultwarden_status-v2/releases/tag/v1.0.0 |
| AdGuard Home Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-adguard_home-v2/releases/tag/v1.0.0 |
| Samba Backup Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-samba_backup-v2/releases/tag/v1.0.0 |
| Supervisor Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-supervisor_status-v2/releases/tag/v1.0.0 |
| Node-RED Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-nodered_status-v2/releases/tag/v1.0.0 |
| Frigate Events v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-frigate_events-v2/releases/tag/v1.0.0 |
| Piper TTS v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-piper_tts-v2/releases/tag/v1.0.0 |
| Whisper STT v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-whisper_stt-v2/releases/tag/v1.0.0 |
| OpenWakeWord Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-openwakeword-v2/releases/tag/v1.0.0 |
| Ukraine Alarm v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-ukraine_alarm-v2/releases/tag/v1.0.0 |
| Nova Poshta v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-nova_poshta-v2/releases/tag/v1.0.0 |
| Ukrposhta Tracking v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-ukrposhta_tracking-v2/releases/tag/v1.0.0 |
| SaveEcoBot Air Quality v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-saveecobot_air-v2/releases/tag/v1.0.0 |
| qBittorrent Status v2 | `v1.0.0` | https://github.com/mambursoft/majordomo-qbittorrent_status-v2/releases/tag/v1.0.0 |

Архивы собираются через GitHub Actions при пуше тега `v*`; у части репозиториев архив публикуется как artifact workflow `build-package.yml`. Проверяйте состав архива перед установкой.

## Установка

1. Скачайте `tar.gz` из раздела Releases нужного репозитория (или используйте URL пакета в маркете Connect).
2. Распакуйте архив в корень MajorDoMo.
3. Откройте «Настройки» в панели управления.
4. Включите модуль и ознакомьтесь с мануалом в его интерфейсе.
5. Если это v2, отключите исходный модуль: две версии не работают одновременно.

## Мануалы

- Общий мануал по каждому модулю: `docs/MANUAL.md` в репозитории модуля.
- Пункт «Manual» доступен в админке соответствующего модуля.
- Вопросы и предложения: Issues в репозитории модуля или https://github.com/sergejey/majordomo/issues

## Обратная связь

Если нашли проблему — открывайте issue в конкретном репозитории. Пожалуйста, указывайте версию PHP, версию MajorDoMo и шаги воспроизведения.
