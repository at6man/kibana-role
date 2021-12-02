Kibana role
=========

Роль для установки Kibana на хостах с ОС: Debian, Ubuntu, CentOS, RHEL.

Requirements
------------

Поддерживаются только ОС семейств debian и EL.

Role Variables
--------------

| Variable name | Default | Description |
|----------------|----------|-------------------------|
| kibana_version | "7.14.0" | Kibana какой версии будет установлена |
|----------------|----------|-------------------------|
| kibana_install_type | remote | Тип установки: remote или local |
|----------------|----------|-------------------------|
| elasticsearch_hosts | `'["http://{{ ansible_facts['default_ipv4']['address'] }}:9200"]'` | Строка в формате JSON-массива, в элементах которого надо указать хосты Elascticsearch. Значение по умолчанию используется, только если Elascticsearch находится на том же хосте, что и Kibana; иначе надо указать другие хосты. |

Example Playbook
----------------

    - hosts: all
      roles:
         - kibana-role

License
-------

MIT
