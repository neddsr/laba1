<!--- Шаблон к оформлению домашней работы -->

## Домашнее задание

**Студента группы ИУ8-22**
**Леонов Никита Никитич**


1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
```sh
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
<вывод команды>
```
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
```sh
$ tar -xf boost_1_69_0.tar.gz -C ~
<вывод команды>
```
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
```sh
$ cd ~/boost_1_69_0
$ find -maxdepth 1 ! -type d  | wc -l
16
```
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
```sh
$ find -type f | wc -l
61813
```
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
```sh
$ find ! -type d -name "*.h" | wc -l; find -type f -name "*.cpp" | wc -l; find -type f ! -name "*.cpp" ! -name "*.h" | wc -l
296
13786
47731
```
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
```sh
$ find -name "any.hpp"
./boost/type_erasure/any.hpp
./boost/fusion/include/any.hpp
./boost/fusion/algorithm/query/any.hpp
./boost/fusion/algorithm/query/detail/any.hpp
./boost/proto/detail/any.hpp
./boost/any.hpp
./boost/hana/fwd/any.hpp
./boost/hana/any.hpp
./boost/spirit/home/support/algorithm/any.hpp
./boost/xpressive/detail/utility/any.hpp
```
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
```sh
$ <команда с необходимыми ключами>
<вывод команды>
```
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
```sh
$ <команда с необходимыми ключами>
<вывод команды>
```
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
```sh
$ <команда с необходимыми ключами>
<вывод команды>
```
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```sh
$ <команда с необходимыми ключами>
<вывод команды>
```
11. Найдите *топ10* самых "тяжёлых".
```sh
$ <команда с необходимыми ключами>
<вывод команды>
```
