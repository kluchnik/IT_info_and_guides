# Запись и воспроизведение действий в браузере

Цель: 
- Упростить процесс записи действий выполняемых при настройке устройств  
- Быстрое повторное воспроизведение действий  
- Использовать записанных действий для формирования тестовых сценариев и автотрестов  
- Ускорение процесса воспроизведения проблем и ошибок  

## Инструмент: Katalon Recorder  
#### Установка:
Устанавливается как расширение для браузеров Chrome и FireFox: https://www.katalon.com/katalon-recorder-ide/
#### Дополнительная информация:
https://docs.katalon.com/katalon-studio/videos/working_with_katalon_recorder.html  
https://docs.katalon.com/katalon-recorder/docs/selenese-selenium-ide-commands-reference.html  
#### Пример использования:
1. Производим разворачивание тестируемой системы с настройками по умолчанию  
> Важно!!! Для корректного воспроизведения записанных действий на разных компьютерах и в разных развернутых системах, их настройки должны совпадать. По умолчанию используем базовые настройки после установки системы.  
>
2. В браузере запускается расширение Katalon Recorder  
![Запуск Katalon Recorder](./img/KR1.jpg)  
3. Создается новый тестовый сценарий с именем, которое описывает производимые настройки  
![Создать новый тестовый сценарий](./img/KR2.jpg)  
В результате должен быть создан новый тестовый сценарий  
![Отображение тестового сценария](./img/KR3.jpg)  
4. Добавляется описание тестового сценария и тестового окружения  
![Добавление команды](./img/KR4.jpg)  
![Задание параметров команды](./img/KR5.jpg)  
echo – команда, которая выводит информационное сообщение в лог, можно использовать как комментарий к действия скрипта.  
5. Записываем производимые действия на странице  
Запускаем запись наших действий:  
![Запуск записи действий](./img/KR6.jpg)  
В браузере выполняем настройку:  
![Выполнение действий в браузере](./img/KR7.jpg)  
Останавливаем запись наших действий:  
![Останов записи действий](./img/KR8.jpg)  
6. Производим удаление избыточных действий и добавляем комментарии к действиям  
![Удаление избыточных действий](./img/KR9.jpg)  
Важно!!! Если поле для настроек находится в не видимости браузера (отсутсвует рендеринг изображения), то может возникать ошибка:  
![Ошибка определения объекта](./img/KR10.jpg)  
Для ее исправления необходимо вручную добавить команду focus:  
![Добавление команды focus](./img/KR11.jpg)  
focus – команда позволяющая переходить на выбранный элемент  
7. Сохранение записанных действий  
![Сохранение сценария](./img/KR12.jpg)  
Сохраняем в формате html:  
![Сохранение](./img/KR13.jpg)  
8. Загрузка записанных действий    
![Загрузка сценария](./img/KR14.jpg)  
9. Воспроизведение записанных действий  
![Воспроизведение сценария](./img/KR15.jpg)  
При необходимости можно уменьшить скорость воспроизведения действий:  
![Регулирование скорости](./img/KR16.jpg)  
10. Экспорт в системы автоматизации тестирования    
![Экспорт в виде кода](./img/KR17.jpg)  
