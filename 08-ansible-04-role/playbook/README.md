# Clickhouse+Vector+Lighthouse Installation

Этот playbook устанавливает и настраивает ClickHouse (СУБД), Vector (агент сбора и обработки логов), Lighthouse (UI для ClickHouse) на целевых хостах.

## Описание

Playbook выполняет следующие задачи:

**ClickHouse** - скачивает и устанавливает ClickHouse сервер, создает базу данных

**Vector** - устанавливает Vector для сбора и обработки логов сервера syslog с последующей отправкой в ClickHouse

**Lighthouse** - устанавливает веб-сервер nginx и GUI для Clickhouse

## Требования

- Ansible 2.9+
- CentOS 7/8, аналогичные RPM-дистрибутивы
- Доступ в интернет для скачивания пакетов
- Права sudo на целевых хостах

## Теги

- `clickhouse` — установка и настройка ClickHouse
- `vector` - установка и настройка Vector
- `lighthouse` - установка и настройка Lighthouse

## Использование

```bash
# Установка и настройка всех сервисов
ansible-playbook -i inventory/prod.yml site.yml

# Установка и настройка только ClickHouse
ansible-playbook -i inventory/prod.yml site.yml --tags clickhouse

# Установка и настройка только Vector
ansible-playbook -i inventory/prod.yml site.yml --tags vector

# Установка и настройка только Lighthouse
ansible-playbook -i inventory/prod.yml site.yml --tags lighthouse
