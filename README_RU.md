# Swaggervel (OpenApi для Laravel 9)

Это комбинация пакетов
[Swagger-php](https://github.com/zircote/swagger-php)
[swagger-ui](https://github.com/swagger-api/swagger-ui)
в один Laravel-friendly пакет.

## Принцип работы

При запуске в режиме debug, пакет сканирует папку `'app-dir' => 'app/Http/Controllers'`
ищёт там соответствующие анатации описывающие функции контролера
и сохраняет сформированный для Swagger/OpenApi json файл в папке `'doc-dir' => storage_path('docs')`
Затем swagger-ui для своей работы использует этот json.

## Установка

- `composer require laravel-russian/swaggervel --dev` добавить в разработку
- Добавить `LaravelRussian\Swaggervel\SwaggervelServiceProvider::class` к массиву провайдеров в `app/config/app.php`, порядок маршрутов провайдеров также важен, надо обращать на это внимание
- `php artisan vendor:publish --tag=public` публикует swagger-ui в публичную папку сервера public/vendor/swaggervel
- `php artisan vendor:publish --tag=config` добавляет config
- `php artisan vendor:publish --tag=views` добавляет используемые views в resources `resources/views/vendor/swaggervel`

## Роуты доступа

- /docs покажет json файл
- /api/docs доступ к самому Swagger UI

## Опции и конфиг

Все изменяемые опции находятся в файле конфигурации `/config/swaggervel.php`
