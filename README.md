# bash

This repository contains some bash commands that I used to do tasks during my Quality Assurance studies.

## Task 1

## Working with files and directories

1. Открыть домашнюю директорию
2. Определить имя папки, в которой вы находитесь

tanyapetruchok@MacBook-Pro-Tana ~ % pwd
/Users/tanyapetruchok
tanyapetruchok@MacBook-Pro-Tana ~ % cd  /Users/tanyapetruchok/Documents/functional_testing

3. Создать внутри этой папки каталог  с именем test1

tanyapetruchok@MacBook-Pro-Tana functional_testing % mkdir test1

4. Перейти в папку test1

tanyapetruchok@MacBook-Pro-Tana functional_testing % cd test1

5. Создать файл 1,2 и 3 внутри каталога test1
6. Проверить содержимое каталога test1

tanyapetruchok@MacBook-Pro-Tana test1 % touch 1.json 2.json 3.json
tanyapetruchok@MacBook-Pro-Tana test1 % ls
1.json,	2.json,	3.json

7. Перейти в домашнюю директорию

tanyapetruchok@MacBook-Pro-Tana test1 % cd - 
~/Documents/functional_testing

8. Создать папку test2 внутри домашней директории

tanyapetruchok@MacBook-Pro-Tana functional_testing % mkdir test2

9. Удалить папку test2

tanyapetruchok@MacBook-Pro-Tana test1 % cd -
~/Documents/functional_testing
tanyapetruchok@MacBook-Pro-Tana functional_testing % rmdir test2

10. Удалить файл 2 из папки test1

tanyapetruchok@MacBook-Pro-Tana functional_testing % cd test1
tanyapetruchok@MacBook-Pro-Tana test1 % rm 2.json

11. Создать папку в домашней директории test3 и добавить в нее два файла

tanyapetruchok@MacBook-Pro-Tana test1 % cd -
~/Documents/functional_testing
tanyapetruchok@MacBook-Pro-Tana functional_testing % mkdir test3 
tanyapetruchok@MacBook-Pro-Tana functional_testing % cd test3
tanyapetruchok@MacBook-Pro-Tana test3 % touch message.html message2.html

12. Удалить папку test3

tanyapetruchok@MacBook-Pro-Tana functional_testing % rm -rf test3

13. Создать папку test4 в домашней директории

tanyapetruchok@MacBook-Pro-Tana functional_testing % mkdir test4
tanyapetruchok@MacBook-Pro-Tana functional_testing % cd test4
tanyapetruchok@MacBook-Pro-Tana test4 % cd - 
~/Documents/functional_testing

14. Переместить файлы 1 и 3 из папки test1 в папку test4

tanyapetruchok@MacBook-Pro-Tana functional_testing % mv test1/1.json test1/3.json test4
tanyapetruchok@MacBook-Pro-Tana functional_testing % ls test4
1.json	3.json

15. Добавить в файл 1 три строки со словами line
16. Посмотреть содержимое файла 1

tanyapetruchok@MacBook-Pro-Tana functional_testing % cd test4 
tanyapetruchok@MacBook-Pro-Tana test4 % nano 1.json
tanyapetruchok@MacBook-Pro-Tana test4 % cat 1.json
line
line
line

17. Добавьте в файл 3 три строки со словами line
18. Просмотрите содержимое двух файлов (1 и 3) сразу

tanyapetruchok@MacBook-Pro-Tana test4 % nano 3.json
tanyapetruchok@MacBook-Pro-Tana test4 % cat 1.json 3.json
line
line
line
line
line
line

19. Используя один из редакторов замените все строки в файле 1

tanyapetruchok@MacBook-Pro-Tana test4 % nano 1.json
tanyapetruchok@MacBook-Pro-Tana test4 % cat 1.json
line1
line2
line3
tanyapetruchok@MacBook-Pro-Tana test4 % 

## Task 2
## Editing files, checking and killing proccesses, pinging websites


1. Зайти в домашнюю директорию

Last login: Mon Aug 21 22:18:56 on ttys031
tanyapetruchok@MacBook-Pro-Tana ~ % pwd
/Users/tanyapetruchok
tanyapetruchok@MacBook-Pro-Tana ~ % cd documents
tanyapetruchok@MacBook-Pro-Tana documents % cd functional_testing
tanyapetruchok@MacBook-Pro-Tana functional_testing % pwd
/Users/tanyapetruchok/documents/functional_testing


2. Создать папку test 3

tanyapetruchok@MacBook-Pro-Tana functional_testing % mkdir test3

4. Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4

tanyapetruchok@MacBook-Pro-Tana test3 % echo -e "row1\nrow2\nrow3\nrow4" >> 4.txt
tanyapetruchok@MacBook-Pro-Tana test3 % cat 4.txt
row1
row2
row3
row4
tanyapetruchok@MacBook-Pro-Tana test3 % cp 4.txt 5.txt
tanyapetruchok@MacBook-Pro-Tana test3 % cp 4.txt 6.txt
tanyapetruchok@MacBook-Pro-Tana test3 % cat 4.txt 5.txt 6.txt
row1
row2
row3
row4
row1
row2
row3
row4
row1
row2
row3
row4

5. Найдите строку row2 в файле 5

tanyapetruchok@MacBook-Pro-Tana test3 % grep -i "row2" 5.txt
row2

6. Найдите строку row в папке test3
tanyapetruchok@MacBook-Pro-Tana test3 % grep -R "row" .    
./5.txt:row1
./5.txt:row2
./5.txt:row3
./5.txt:row4
./4.txt:row1
./4.txt:row2
./4.txt:row3
./4.txt:row4
./6.txt:row1
./6.txt:row2
./6.txt:row3
./6.txt:row4


7. Посчитайте сколько строк с содержимым row в файле 6

tanyapetruchok@MacBook-Pro-Tana test3 % grep -c "row" 6.txt
4

8. Найдите файл 5 внутри папки test3

tanyapetruchok@MacBook-Pro-Tana test3 % find 5.txt
5.txt

9. Используя команду find, удалите файл 5

tanyapetruchok@MacBook-Pro-Tana test3 % find 5.txt -delete
tanyapetruchok@MacBook-Pro-Tana test3 % ls
4.txt	6.txt


10. Используя команду echo, добавьте слово test в файл 4

tanyapetruchok@MacBook-Pro-Tana test3 % echo test > 4.txt
tanyapetruchok@MacBook-Pro-Tana test3 % cat 4.txt
test


11. Замените слово test в файле 4 на fail

tanyapetruchok@MacBook-Pro-Tana test3 % sed -i '' -e  "s/test/fail/" 4.txt 
tanyapetruchok@MacBook-Pro-Tana test3 % cat 4.txt
fail


12. Добавьте в файл 4 слово test так, чтобы сохранилось содержимое

tanyapetruchok@MacBook-Pro-Tana test3 % echo test >> 4.txt
tanyapetruchok@MacBook-Pro-Tana test3 % cat 4.txt
fail
test


13. Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе
tanyapetruchok@MacBook-Pro-Tana test3 % ps aux

14. Убейте процесс 666 в консоли
tanyapetruchok@MacBook-Pro-Tana test3 % kill 666
kill: kill 666 failed: no such process

15. Узнайте доступность ресурса artsiomrusau.com, используя ping

tanyapetruchok@MacBook-Pro-Tana test3 % ping artsiomrusau.com
PING artsiomrusau.com (185.215.4.92): 56 data bytes
Request timeout for icmp_seq 0
Request timeout for icmp_seq 1
Request timeout for icmp_seq 2

16. Отправьте 5 пакетов на сайт artsiomrusau.com

tanyapetruchok@MacBook-Pro-Tana ~ % ping -c 5 artsiomrusau.com 
PING artsiomrusau.com (185.215.4.92): 56 data bytes
Request timeout for icmp_seq 0
Request timeout for icmp_seq 1
Request timeout for icmp_seq 2
Request timeout for icmp_seq 3

--- artsiomrusau.com ping statistics ---
5 packets transmitted, 0 packets received, 100.0% packet loss

17. Используя GET и команду curl, получите информацию о зарегистрированных питомцах на https://petstore.swagger.io/

tanyapetruchok@MacBook-Pro-Tana ~ % curl --location 'https://petstore.swagger.io/v2/pet/findByStatus?status=available' \
--header 'api_key: special-key'
[{"id":9223372036854769163,"category":{"id":0,"name":"string"},"name":"fish","photoUrls":["string"],"tags":[{"id":0,"name":"string"}],"status":"available"},{"id":9223372036854769164,"category

etc

18. Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/

tanyapetruchok@MacBook-Pro-Tana ~ % curl -X POST --location 'https://petstore.swagger.io/v2/user' \
--header 'Content-Type: application/json' \
--header 'api_key: special-key' \
--data-raw '
{
  "id": 798,
  "username": "Vanessa",
  "firstName": "Max",
  "lastName": "Keil",
  "email": "Jayne_Schultz14@yahoo.com",
  "password": "123",
  "phone": "1234534",
  "userStatus": 1
}'
{"code":200,"type":"unknown","message":"798"}%                                  tanyapetruchok@MacBook-Pro-Tana ~ % 
tanyapetruchok@MacBook-Pro-Tana ~ % curl --location 'https://petstore.swagger.io/v2/user/Vanessa' \
--header 'api_key: special-key' \
> 
{"id":798,"username":"Vanessa","firstName":"Max","lastName":"Keil","email":"Jayne_Schultz14@yahoo.com","password":"123","phone":"1234534","userStatus":1}% 
