# Проект AnsibleDockView

## Обзор

AnsibleDockView - это проект, предназначенный для мониторинга систем с использованием Docker контейнеров, оркестрированных и автоматизированных с помощью Ansible. В проект включены инструменты для сбора и визуализации метрик, система управления событиями и уведомлениями, а также настройка, гарантирующая работу всего в Docker контейнерах.

За дополнительной информацией обращайтесь к документации в директории `docs`.

## Требования

- Ansible
- Git

## Документация

Для углубленного понимания и использования данного проекта, ознакомьтесь с дополнительной документацией:

- [Инструкции по использованию](docs/usage.md): Подробное руководство по использованию и управлению системой, описывающее процесс запуска Ansible playbook, проверку состояния контейнеров и взаимодействие с компонентами системы.
  
- [Инструкции по установке](docs/installation.md): Шаг за шагом описывает процесс установки и настройки всех компонентов системы.

- [Описание архитектуры](docs/architecture.md): Объясняет структуру и дизайн системы, предоставляет информацию о роли каждого компонента и описывает, как они работают вместе.

## Структура Директорий

```
AnsibleDockView/
├── README.md
├── docs/
│   ├── architecture.md
│   ├── installation.md
│   └── usage.md
└── ansible/  
    ├── inventory.yml
    ├── playbook.yml
    ├── ansible.cfg
    ├── roles/  
    │   ├── configure_alertmanager/
    │   ├── configure_elk/
    │   ├── configure_filebeat/
    │   ├── configure_grafana/
    │   ├── configure_prometheus/
    │   ├── install_docker/
    │   └── start_docker_compose/  
    ├── files/  
    │   ├── alertmanager/
    │   ├── docker-compose/
    │   │   ├── monitored-host/
    │   │   └── monitoring-host/
    │   ├── elk/
    │   │   ├── elasticsearch/
    │   │   ├── kibana/
    │   │   └── logstash/
    │   ├── filebeat/
    │   ├── grafana/
    │   └── prometheus/ 
    └── group_vars/
        └── all.yml
```

## Лицензия

Этот проект лицензирован в соответствии с лицензией MIT. За подробностями обращайтесь к файлу LICENSE в корневой директории этого проекта.

## Контакты и Вклад

Если у вас есть вопросы или предложения, пожалуйста, создайте issue в репозитории GitHub. Мы также приветствуем ваши вклады, поэтому не стесняйтесь создавать pull request.

## Ресурсы и Дополнительная Информация

Для получения дополнительной информации о конфигурации и использовании каждого инструмента обратитесь к конфигурационным файлам в соответствующих директориях. Если вы вносите изменения в конфигурационные файлы, вам потребуется перезапустить соответствующие контейнеры, чтобы изменения вступили в силу.
