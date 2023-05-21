**Набор ролей:**

| role             | description                                                                                                                                          |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| haproxy_balancer | установка и настройка haproxy в качестве балансировщика запросов к кластеру mariadb. Включается переменной balancer_present в group_vars/mariadb.yml |
| mariadb_db       | создание баз данных, определенных в переменной mysql_users (group_vars/mariadb.yml)                                                                  |
| mariadb_config   | обновление файла конфигурации mariadb                                                                                                                |
| mariadb_install  | установка пакетов mariadb                                                                                                                            |
| mariadb_replica  | настройка репликации master-slave                                                                                                                    |
| mariadb_secure   | настройки безопасности mariadb (удаление анонимных юзеров, тестовый БД)                                                                              |
| mariadb_user     | создание пользователей БД с назначением прав. Определены в переменной mysql_users (group_vars/mariadb.yml)                                           |



Playbook использует hcl vault для хранения секретов. Чтобы использовать свой инстанс hcl vault в среде запуска playbook необходимо определить переменные окружения:

`export ANSIBLE_HASHI_VAULT_USERNAME="<login>"
export ANSIBLE_HASHI_VAULT_PASSWORD="<passwd>"
export VAULT_ADDR="http://<host>:8200"`

а также установить модуль для python:
`pip3 install -r requirements.txt`



*todo:**

- добавить настройку firewall/iptables

- добавить скрипт для создание бекапов
