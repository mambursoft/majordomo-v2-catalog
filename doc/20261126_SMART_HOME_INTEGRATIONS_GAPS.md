# Анализ направлений интеграций: Tuya, Xiaomi, ONVIF, Zigbee, SSDP, Google Cast, openHASP, MegaD

Дата: 2026-11-26  
Статус: фактический анализ для планирования модулей MajorDoMo v2  
Источники: документация Home Assistant, OpenHAB, проекты сообщества, репозитории MajorDoMo и собственные пакеты v2.

## 1. Метод

Для каждого направления сравниваются:

- реализация в Home Assistant (штатная и community-интеграции);
- реализация в других открытых системах (OpenHAB, HACS-проекты);
- текущее состояние MajorDoMo (ядро + наши v2-пакеты);
- практические нюансы, которыедолжен в модуле;
- решение: улучшить существующий модуль или создать новый.

## 2. Tuya

**Home Assistant.** Штатная интеграция `tuya` — облачная (Cloud Push): авторизация через Tuya Smart / Smart Life,device ID и local key получаются из облака. Community-проекты `tuya-local` и `LocalTuya` работают по LAN и требуют device ID, IP/имя хоста, local key и версию протокола. `tuya-local` использует готовые конфигурации device type, `LocalTuya` — ручное картирование data points (DP). Не все устройства поддерживают локальный режим, а часть функций доступна только в облаке.

**Другие системы.** OpenHAB использует отдельный Tuya binding с облачным мостом; локальное управление обычно строится через MQTT-шлюз.

**MajorDoMo.** В ядре отдельного модуля нет; наш `majordomo-tuya-v2` убирает вызовы Python/exec и работает через локальный мост. Текущая версия не хранит device ID, local key, protocol version и таблицу DP.

**Нюансы для модуля:**

- различать облачный и локальный режимы;
- хранить `device_id`, `local_key`, `protocol` и `device_ip`;
- DP-картирование должно быть конфигурируемым, а не жёстко заданным;
- при отсутствии local key модуль должен честно сообщать, что доступен только облачный статус;
- не логировать local key.

**Решение:** улучшить `majordomo-tuya-v2`: добавить поля локального режима и DP-карты в шаблон настройки и API.

## 3. Xiaomi

**Home Assistant.** Два разных контура: `xiaomi_miio` (локальный miIO-протокол, device ID + token) и Xiaomi Miot Auto / `xiaomi_miot` ( Mi Home cloud + локальный miot-мост). Важно: часть устройств работает только через cloud, часть — через local miIO, token можно получить только из облака или из резервной копии приложения.

**Другие системы.** OpenHAB использует Xiaomi IO binding и miIO-bridge; community-решения часто комбинируют облачный getting token с локальным управлением.

**MajorDoMo.** Есть наш `majordomo-xiaomimiio-v2` и новый `majordomo-xiaomi_miot_auto-v2`; в ядре — только косвенные интеграции через device classes.

**Нюансы:**

-Различать miIO и Miot: это разные протоколы и разные идентификаторы;
- token чувствителен и не должен попадать в логи;
- device ID можно получить из cloud-ответа; без токена локальный вызов невозможен;
- для Miot требуется `did` и модель устройства;
- состояние some устройств приходит только по push, а не по опросу.

**Решение:** улучшить оба модуля: явно разделить режимы `miio_local`, `miot_cloud`, `miot_local`, добавить поля `did`, `model`, `token` и маску токена в UI.

## 4. ONVIF

**Home Assistant.** Интеграция `onvif` использует ONVIF Device Management для discovery профилей, Media1/Media2 для RTSP-потоков и Events (WS-Notification, PullPoint) для motion/alarm. PTZ — через отдельный PTZ-контроллер. Частая проблема: камера отдает несколько профилей с разным разрешением и framerate; RTSP-адрес не равен ONVIF endpoint; события требуют подписки и переподписки.

**Другие системы.** Frigate ориентирован на RTSP + motion detection; ONVIF используется только как источник потока и PTZ. OpenHAB ONVIF binding предоставляет камеру, PTZ и события.

**MajorDoMo.** В ядре есть `SCameras` (снимки, motion-свойства), но нет ONVIF-профилей и подписки на события.

**Нюансы:**

- хранить `onvif_endpoint`, `profile_token`, `rtsp_url`, `events_mode`;
- различать static snapshot и RTSP;
- события motion нужно переводить в свойства объекта `SCameras`;
- PTZ должен быть отдельным action, а не частью статуса.

**Решение:** создать `majordomo-onvif-v2` с профилями, RTSP, событиями и PTZ-действиями.

## 5. Zigbee

**Home Assistant.** ZHA и Zigbee2MQTT — две основные школы. Z2M дает MQTT-топики `zigbee2mqtt/<friendly_name>` и JSON с состоянием; важен `device map`, `coordinator state`, OTA, binding и groups. HA-интеграция Zigbee2MQTT обменивается через MQTT discovery.

**Другие системы.** OpenHAB Zigbee binding работает через отдельный coordinator; Node-RED часто используется как шина между Z2M и системой автоматизации.

**MajorDoMo.** Есть наш `majordomo-mqtt-v2` и `majordomo-zigbee2mqtt_status-v2`; последний сейчас проверяет только состояние координатора.

**Нюансы:**

- friendly_name может отличаться от IEEE address;
- топики availability и state нужно обрабатывать раздельно;
- устройства с батарейкой не отвечают на immediately opros;
- OTA и binding требуют отдельных AJAX-операций.

**Решение:** расширить `zigbee2mqtt_status-v2` до карты устройств и операций binding/OTA.

## 6. SSDP / UPnP

**Home Assistant.** Интеграция `ssdp` сканирует сеть через M-SEARCH и автоматически discovering совместимые интеграции; `upnp` собирает statistics с IGD (bytes/packets, uptime, WAN IP, connectivity). Распространенная проблема — повторное появление проигнорированных устройств.

**Другие системы.** OpenHAB UPnP binding использует similar discovery; для отладки используют SSDP/UPnP browser.

**MajorDoMo.** SSDP-дискавери в ядре нет.

**Нюансы:**

- M-SEARCH — UDP multicast 239.255.255.250:1900, нужен timeout и dedup по USN;
- устройства могут отвечать с задержкой;долженвыполнять 2-3 попытки;
- IGD требует XML-описания и control URL;
- ignore-list должна храниться в настройках и не сбрасываться при перезапуске.

**Решение:** создать `majordomo-ssdp-v2`: discovery, ignore-list, IGD-статус.

## 7. Google Cast (Nest Mini, JBL Link)

**Home Assistant.** Интеграция `cast` работает через mDNS/_googlecast._tcp и локальный HTTP `:8008`. При проблемах с VLAN/mDNS помогает ручной список hostnames/IP. Поддерживаются media_player, TTS, volume, app_id. Важно различать Cast-протокол и Google Assistant (Nest integration) — это разные вещи.

**Другие 시스템.** В MajorDoMo ядре уже есть `app_player/libs/castv2` и mDNS-помощник — база есть, но нет отдельного модуля статуса и управления для Nest Mini/JBL Link.

**Нюансы:**

- устройство может не отвечать на mDNS в другом VLAN;
- нужен fallback по IP;
- TTS через Cast требует URL локального аудиофайла, а не текста;
- состояние плеера может быть `idle`, `playing`, `paused`, `buffering`;
- для JBL Link часть функций доступна только через Cast, не через Nest.

**Решение:** создать `majordomo-google_cast-v2` с ручным адресом, mDNS-подсказкой, статусом и TTS-вызовом через локальный файл.

## 8. openHASP

**Home Assistant.** Community-интеграция openHASP синхронизирует объекты панели через MQTT (pre discovery). Каждый объект hasp/<device>/obj<id> имеет properties (`val`, `txt`, `visible`), команды идут в `hasp/<device>/command`. Важно хранить mapping «объект панели → свойство MajorDoMo».

**Другие системы.** OpenHAB использует MQTT binding с похожей схемой топиков.

**MajorDoMo.** Отдельного модуля нет.

**Нюансы:**

- device name в топике не равен IP;
- page/obj id нужно хранить как строку;
-своё свойство можно и читать, и писать; нужен debounce;
- при перезагрузке панели состояние нужно восстановить из MajorDoMo.

**Решение:** создать `majordomo-openhasp-v2` с MQTT-мостом и mapping объектов.

## 9. MegaD

**Home Assistant.** HACS-интеграция `mega_hacs` поддерживает MegaD-2561/328: автоматическое добавление портов (lights, PWM lights, binary sensors, sensors), RGB/W и ws28xx, smooth dimming, несколько контроллеров, HTTP callback, восстановление состояний после перезагрузки, двойные/долгие нажатия, serial execution команд без конкурентного доступа, расширители и I2C-ANY. Ключевой нюанс — команды отправляются только после ответа предыдущей.

**Другие системы.** openHAB binding для MegaD-2561/328 также строится вокруг HTTP API контроллера.

**MajorDoMo.** Separate module in core is absent; управление обычно делается через scripts и objects вручную.

**Нюансы:**

- endpoint имеет вид `http://<ip>/<sec>/?cmd=<port>:<value>`;
- `sec` — секрет контроллера, чувствителен;
- порты 0..N имеют разные режимы (IN, OUT, PWM, ADC, I2C);
-lash responses и callback (входящие HTTP от контроллера) требуют отдельного endpoint;
- concurrency: команды нельзя отправлять параллельно;
- extended boards (16I-XT, 16R-XT, 16PWM) и ds2413 нужно учитывать в модели порта;
- после перезагрузки контроллера состояния выходов нужно восстановить.

**Решение:** создать `majordomo-megad-v2` с очередью команд, типами портов, callback endpoint и восстановлением состояний.

## 10. Порядок внедрения и защита GitHub

Новые репозитории создавать **с интервалом по времени** (минимум 60–90 секунд между созданиями; при `403 secondary rate limit` — пауза 10 минут и одна повторная попытка, согласно §7 регламента `doc/20261123_GITHUB_WORKFLOW.md`).

1. Улучшить `tuya-v2`, `xiaomimiio-v2`, `xiaomi_miot_auto-v2`, `zigbee2mqtt_status-v2`.
2. Создать `onvif-v2`, `ssdp-v2`, `google_cast-v2`, `openhasp-v2`, `megad-v2` с интервалом.
3. Для каждого модуля — подробные описания RU/EN и скриншот страницы настроек.
4. Сводный Issue в ядре с таблицей направлений и ссылками на репозитории.
