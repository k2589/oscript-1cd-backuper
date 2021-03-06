# oscript-1cd-backuper

*Простой набор скриптов для бэкапа и копирования на FTP файловой базы 1С в SOHO*

## Функции

1. Копирование файла 1cv8.1cd в локальную папку бэкапа
2. Загрузка данного файла на FTP сервер
3. Оповещение в телеграм о происходящих операциях

## Мотивация

Было необходимо создать систему бэкапа базы в нашем небольшом офисе для снижения рисков от вирусов-шифровальщиков.  
Стало интересно попробовать в деле onescript и создать open source проект.  

Далее планируется, что проект обрастет следующими функциями:

* Перемещение бэкапа вглубь сервера на котором развернут FTP (чтобы он не был доступен с windows машин)
  
* Контроль сроков хранения бэкапов (удаление старше n дней/месяцев)

* Тестирование состояний бэкапов (автоматическое разворачивание и *какая-нибудь проверка*)

## Начало работы

1. Клонируйте или скачайте себе репозиторий
2. Создайте копию файла *param_os_default.json* 
3. Переименуйте его в *param_os.json* и заполните все параметры
4. Добавьте в планировщик заданий команду `oscript "/путь до/runner.os"` и настройте раписание
5. Enjoy!

>В файле *param_os.json* хранятся пароли, поэтому он добавлен в .gitignore.  
> __Не храните пароли и конфиденциальные сведения в *param_os_default.json*!__

## Требуемые библиотеки

* Fs
* Configor
* 1commands
* Messenger
* FTP *(не ниже версии 1.0.3)*

> FTP 1.0.3 пока не доступен в opm, необходимо скачать его [из репозитория](https://github.com/dmpas/oscript-ftp/releases/tag/v1.0.3-alpha1) и установить через команду  
>`opm install -f /путьКФайлу/ftp-1.0.3.ospx`

>Скрипт проверен на работоспособность с oscript версии 1.1.1.42.

## Contributors

Я буду рад вашим PR и issues.  
Улучшение кода и дополнение функциональности приветствуется!

Я пока не разобрался с написанием тестов для кода, поэтому также крайне приветсвтуется помощь с тестами.

## Лицензия

Распростроняется под лицензией Mozilla Public License 2.0.  
Текст лицензии в файле LICENSE.
