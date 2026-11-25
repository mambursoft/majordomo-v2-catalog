# Анонс пакетов v2 (для форума и Connect)

## Заголовок

Модули MajorDoMo v2: MQTT, Tuya, Xiaomi miIO и Google Location

## Текст

Подготовил отдельные пакеты v2 для четырех модулей MajorDoMo. Это не обновление оригинальных модулей, а самостоятельные версии с суффиксом v2. Их можно устанавливать вместо исходных, но не вместе с ними.

Что сделано:

- убраны вызовы Python и exec из ядерных путей Tuya и Xiaomi;
- добавлена проверка прав доступа к AJAX-операциям;
- исправлена конкуренция за id.json через flock;
- сохранены пароли и токены в настройках;
- добавлены локализации en/ru/uk;
- интерфейс адаптирован под телефоны;
- архивы собираются автоматически через GitHub Actions.

Каталог и мануалы: https://github.com/mambursoft/majordomo-v2-catalog

Релизы:

- MQTT v2: https://github.com/mambursoft/majordomo-mqtt-v2/releases/tag/v2.0.0
- Tuya v2: https://github.com/mambursoft/majordomo-tuya-v2/releases/tag/v2.0.0
- Xiaomi miIO v2: https://github.com/mambursoft/majordomo-xiaomimiio-v2/releases/tag/v2.0.0
- Google Location v2: https://github.com/mambursoft/majordomo-google-location-v2/releases/tag/v2.0.0

Если найдете проблемы — открывайте issue в соответствующем репозитории. Указывайте версию PHP и шаги воспроизведения.