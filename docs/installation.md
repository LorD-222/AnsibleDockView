# Установка

Это руководство проведет вас через процесс настройки проекта AnsibleDockView.

## Предварительные Требования

- Ansible
- Git

## Шаги по Установке

1. Клонируйте репозиторий на свой локальный компьютер с помощью команды Git: `git clone URL-репозитория`.

2. Перейдите в директорию проекта: `cd AnsibleDockView`.

## Настройка

### Ansible

- **Файл `inventory.yml`**: Укажите свои узлы Ansible и группы в этом файле.
- **Файл `playbook.yml`**: Этот файл содержит основной playbook для Ansible. Проверьте его и внесите необходимые изменения для вашего сценария.
- **Файл `ansible.cfg`**: Это главный файл конфигурации Ansible. Убедитесь, что он настроен в соответствии с вашим окружением.
- **Настройка директории `group_vars`**: В файле `all.yml` вы должны указать все необходимые переменные для вашей конкретной настройки. Это может включать такие параметры, как адреса IP серверов, логины и пароли, порты и т.д.

### Мониторинг

- **Настройка директории `files`**: 
  - `alertmanager`
    - `alertmanager.yml`: Конфигурационный файл Alertmanager.
  - `docker-compose`
    - `monitored-host`: Содержит файл `docker-compose.yml` для monitored host.
    - `monitoring-host`: Содержит файл `docker-compose.yml` для monitoring host.
  - `elk`
    - `elasticsearch`
      - `elasticsearch.yml`: Конфигурационный файл для Elasticsearch.
    - `kibana`
      - `kibana.yml`: Конфигурационный файл для Kibana.
    - `logstash`
      - `logstash.conf`: Конфигурационный файл для Logstash.
  - `filebeat`
    - `filebeat.yml.j2`: Шаблон для Filebeat берет значения переменных из group_vars.
  - `grafana`
    - `dashboards`
      - `dashboard.yml`: Файл описания дашбордов Grafana.
      - `dashboard1.json`: Дашборд Grafana в формате JSON.
    - `datasources`
      - `datasource.yml`: Файл описания источников данных Grafana.
  - `prometheus` 
    - `alerts.yml`: Файл для настройки оповещений Prometheus.
    - `prometheus.yml`: Общий конфигурационный файл для Prometheus.

После выполнения всех настроек, вы можете запустить проект с помощью Ansible playbook: `ansible-playbook -i inventory.yml playbook.yml`. Эта команда запустит playbook, который автоматически настроит и запустит все Docker контейнеры в соответствии с вашими настройками.
