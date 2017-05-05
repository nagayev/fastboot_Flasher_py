[![Build Status](https://travis-ci.org/zmey3301/fastboot_Flasher_py.svg?branch=master)](https://travis-ci.org/zmey3301/fastboot_Flasher_py)
# fastboot_Flasher_py
На данный момент скрипт умеет:
  1. Прошивать устройства через fastboot согласно конфигурационного файла **config.sst**;
  2. Прошивать устройства через sideload, на данный момент работает только со скачанными через скрипт файлами, либо с файлом '*sideload.zip*';
  3. Скачивать прошивки с сервера, url файла-базы прошивок указывается в файле **config.sst**;
  4. Проверять MD5 суммы скачанных архивов;
  5. Откатывать версию Android с сохранением пользовательского софта и его данных.
# Настройка скрипта:
### config.sst:
1. строка: devices: **< Кодовое имя устройства >** as **< Красивое имя для пользователя >**
    
    Перечисление поддерживаемых устройств через запятую.
    
2. строка: download config url: **< URL файла с информацией для загрузчика прошивок >**
  
    Указывается ссылка на файл с информацией о прошивках, по этой ссылке так же будет проводиться проверка доступности сервера.
    
3. строка: **< Кодовое имя устройства >**
    
    Начало секции устройства, в сроке можно перечислять несколько устройств, если конфигаруция скрипта для них совпадает. Нечувствительно к регистру.
    
4. строка: flash **< Файл >** to **< Раздел >**
  
    Указывает какой файл куда прошивать, файлы обязательно должны находиться в скачиваемых архивах, иначе выполнение будет остановлено. Перечисление пар *Файл to Раздел* через запятую.
    
5. строка: erase **< Раздел >**
  
    Указывает какие разделы необходимо очистить перед прошивкой, none если таких разделов нет.
  
  ##### Cтроки с 3 по 5 повторяются для каждого поддерживаемого устройства.

### download.txt
##### Содержит строки вида **< Кодовое имя устройства > < Имя файла > < MD5 > < Ссылка на файл >**
  1. Кодовое имя устройства не чувствительно к регистру;
  2. Имя файла должно содержать метод прошивки (*fastboot, recovery*), на данный момент тестировались только zip-архивы;
  3. MD5, no comments;
  4. Прямая ссылка на файл.
# TODO:
- [ ] Добавить выбор файла для sideload;
- [ ] Включить adb в bundle;
- [ ] Добавить directoryMode;
- [ ] Добавить возможность обработки bat-файлов для прошивки;
- [ ] Сделать qt5 QUI версию.
## Дополнительная информация:
  Файл errors.txt содержит в себе все коды ошибок скрипта.
