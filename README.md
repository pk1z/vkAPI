# vkAPI - постинг на стену вконтакте.

Пример использования - index.php.
Если указан user_id и group_id берется только user_id.

## Предварительные настройки - получение токена.

    Вам нужно создать Standalone-приложение. С другими работать не будет.
    После - переходите по ссылке 
    https://oauth.vk.com/authorize?client_id=ИД_ВАШЕГО_ПРИЛОЖЕНИЯ&scope=notify,friends,photos,offline,wall&redirect_uri=blank.html&display=popup&response_type=token
    
    После этого копируете из адресной строки token, заполняете все поля и можно запускать.
    Через такой метод можно постить не больше 50 постов в день одному пользователю / группе.\
    Чаще чем раз в 5 минут лучше не постить - банят.

## Установка на Symfony.
 1. Добавить репозиторий в список репозиториев в composer.json
 
    ```
     "repositories": [
         ...
         {
             "type": "package",
             "package": {
                 "name": "pk1z/vkAPI",
                 "version": "1.0.0",
                 "source": {
                     "url": "https://github.com/pk1z/vkAPI",
                     "type": "git",
                     "reference": "master"
                 }
             }
         }
       ]
    ```   
    
 2. Добавить репозиторий в список зависимостей (в require или require-dev)
    
    ```
           "require-dev": {
               ... 
               "pk1z/vkAPI": "*"
           },
    ```
              
 3. Добавить загрузку Namespace в /app/autoload.php
               
    ```
       $loader->add('VkApi', __DIR__.'/../vendor/pk1z/vkAPI/src' );
    ```       