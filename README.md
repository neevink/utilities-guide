# Шпаргалка по утилитам для терминала

## ssh
Позволяет установить ssh-соединение с удалённым хостом.
<br>
Пример работы:
```shell
ssh -p 2222 s313087@helios.se.ifmo.ru
```
- `-p` - ssh-порт
Прокинуть порт через ssh:
```shell
ssh -p 2222 -L 8098:localhost:8098 s313087@helios.se.ifmo.ru
```
- `-L` - прокинуть порт (установить ssh-туннель)

## scp
Позволяет копировать файлы на удалённый хост по shh.
<br>
Пример работы:
```shell
scp -r -P 2222 src s313087@helios.se.ifmo.ru:/home/s313087/web/lab4/
```
- `-r` - рекурсивное копирование (для директорий)
- `-P` - ssh-порт

## grep
Позволяет фильтровать строки при помощи регулярных выражений.
<br>
Пример работы:
```shell
grep -r --include "*.cpp" "pattern"
```
- `-r` - рекурсивный поиск в подкаталогах
- `--include` - в файлах, которые попадают под паттерн

## curl
Позволяет сделать HTTP-запрос к удалённому ресурсу, консольный Postman.
<br>
Пример работы:
```shell
curl -X POST -H "Content-Type: application/json" -d '{"key": "value"}' http://localhost:4321/write?id=777
```
- `-X` - указать метод запроса (GET, POST, PUT, DELETE...)
- `-H` - добавить заголовок (может быть несколько заголовков)
- `-d` - добавить значение в тело запроса

## tar
Утилита для создания архивов файлов и каталогов.
<br>
Пример использования:
```shell
tar xf archive .tar
```
- `x` - достать файлы из архива
- `xf` - достать файлы и каталоги из архива
