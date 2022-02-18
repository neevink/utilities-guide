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

## protoc
Позволяет компилировать `.proto` файлы в файлы с исходным кодом для использования протокола ProtoBuf.
<br>
Пример использования для Python:
```shell
protoc -I=. --python_out=. ./hostsgroups.proto
```
- `I` - директория для импортов protobuf
- `python_out` - где создать `.py` файл
- `java_out` - где создать `.java` файл
- `cpp_out` - где создать `.cpp` файл

## df
disk free - отобразить размер и занятое пространство всех файловых систем
```
df -h
```
- `h` - humal readable, удобочитаемый формат (не в байтах)

## du
disk usage - отобразить размер и занятое пространство файлами в текущей директории
```
du -h -s -d 1
```
- `h` - humal readable, удобочитаемый формат (не в байтах)
- `d` - deep - глубина (насколько глубоко от текущего каталога нужно спускаться вниз и считать размер)
- `s` - summary - отобразить суммарный размер всех файлов


## la, ll
`la` - `ls -a`
`ll` - `ls -l`


## env
Отобразить все переменные окружения


## export
Выставить переменную окружения
```shell
export MY_VARIABLE=12345
```


## ps
processor status - узнать информацию о запущенных процессах
```
ps aux
```
- `a` - all - отобразить все процессы, а не только этого пользователя
- `u` - user-owner - также отображать пользовятеля, которому пренадлежит процесс
- `x` - отобразить прецессы не связанные с текущем процессом терминала



## id
Отобразить инфомацию о текущем пользователе или указанном пользователе
```
id root
```
