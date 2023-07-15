# DockView

## Описание

DockView - это проект, предназначенный для мониторинга и анализа систем, использующих Docker контейнеры. Он включает в себя инструменты для сбора и визуализации метрик, а также систему управления событиями и предупреждениями, все запускаемые в Docker контейнерах.

## Требования

Для работы с проектом вам потребуется:

1. Docker
2. Docker Compose

## Установка и настройка

Для установки и настройки проекта DockView следуйте этим шагам:

1. Клонируйте репозиторий на ваш локальный компьютер.
2. Убедитесь, что у вас установлены Docker и Docker Compose.
3. Перейдите в каталог `monitoring-host`. Здесь вы найдете файл `docker-compose.yml`, который определяет все контейнеры для мониторинга. Настройте конфигурационные файлы каждого сервиса (Prometheus, Alertmanager, Grafana, ELK stack и Filebeat) согласно ваших требований.
4. Далее, перейдите в каталог `monitored-host`. Здесь вы найдете еще один файл `docker-compose.yml`, который определяет контейнеры, которые будут мониториться. Настройте Filebeat в соответствии с вашей системой.
5. После настройки всех контейнеров, вы можете запустить проект, используя Docker Compose.

## Использование

Для использования сервисов мониторинга DockView вам необходимо убедиться, что все контейнеры запущены и работают корректно.

1. Запустите все контейнеры мониторинга из каталога `monitoring-host`, используя команду `docker-compose up`.
2. Запустите контейнеры, которые будут мониториться, из каталога `monitored-host`, также используя команду `docker-compose up`.
3. Убедитесь, что все контейнеры работают корректно, используя команду `docker ps`.

## Структура проекта

```
├── README.md
├── monitoring-host/
│   ├── prometheus/
│   │   ├── prometheus.yml
│   │   └── alerts.yml
│   ├── alertmanager/
│   │   └── alertmanager.yml
│   ├── grafana/
│   │   ├── dashboards/
│   │   │   ├── dashboard.yml
│   │   │   └── dashboard1.json
│   │   └── datasources/
│   │       └── datasource.yml
│   ├── elk/
│   │   ├── logstash/
│   │   │   └── logstash.conf
│   │   ├── elasticsearch/
│   │   │   └── elasticsearch.yml
│   │   └── kibana/
│   │       └── kibana.yml
│   ├── filebeat/
│   │   └── filebeat.yml
│   └── docker-compose.yml
└── monitored-host/
    ├── filebeat/
    │   └── filebeat.yml
    └── docker-compose.yml
```

## Поддержка

Если у вас возникли вопросы или предложения по улучшению проекта, пожалуйста, создайте issue в репозитории GitHub. Мы также приветствуем контрибуции, так что если вы хотите улучшить проект, не стесняйтесь делать pull request.

## Лицензия

Проект распространяется под лицензией MIT. Подробности можно узнать в файле LICENSE в корневом каталоге проекта.
