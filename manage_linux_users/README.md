| role         | description                                                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| manage_users | all in one - создание групп пользователей, создание пользователей, добавление ssh pub ключей пользователям, удаление устаревших пользователей |



Playbook использует hcl vault для хранения секретов. Чтобы использовать свой инстанс hcl vault в среде запуска playbook необходимо определить переменные окружения:

`export ANSIBLE_HASHI_VAULT_USERNAME="<login>"
export ANSIBLE_HASHI_VAULT_PASSWORD="<passwd>"
export VAULT_ADDR="http://<host>:8200"`

а также установить модуль для python:
`pip3 install -r requirements.txt`


