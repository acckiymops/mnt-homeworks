Ansible Playbook: ClickHouse + Vector Installation
Этот playbook устанавливает и настраивает ClickHouse (СУБД) и Vector (агент сбора и обработки логов) на целевых хостах.

Описание
Playbook выполняет следующие задачи:
ClickHouse - скачивает и устанавливает ClickHouse сервер, создает базу данных
Vector - устанавливает Vector для сбора и обработки логов сервера syslog с последующей отправкой в ClickHouse

Требования
Ansible 2.9+
CentOS/RHEL 7/8, аналогичные RPM-дистрибутивы
Доступ в интернет для скачивания пакетов
Права sudo на целевых хостах

Теги
clickhouse — все задачи установки ClickHouse
clickhouse-download — скачивание RPM-пакетов ClickHouse
clickhouse-install — установка пакетов ClickHouse через yum
clickhouse-configure — настройка ClickHouse

vector — все задачи установки Vector
vector-download — скачивание RPM-пакета Vector
vector-install — установка пакета Vector через yum
vector-configure — настройка окружения (пользователь, каталоги, конфиг)
vector-service — настройка службы systemd

Пример использования тегов для выполнения выборочных задач
ansible-playbook -i inventory/prod.yml site.yml --tags vector-service