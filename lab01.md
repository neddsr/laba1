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
$ grep -rl "boost::asio" > task7.txt
```
[вывод команды](https://github.com/neddsr/lab01/blob/main/task7.txt)

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
$ cd ~/boost-libs
$ find -type f -exec du -h {} + | sort -h
4,0K    ./libboost_atomic.a
4,0K    ./libboost_exception.a
4,0K    ./libboost_stacktrace_noop.a
4,0K    ./libboost_system.a
16K     ./libboost_stacktrace_basic.a
20K     ./libboost_context.a
20K     ./libboost_stacktrace_backtrace.a
36K     ./libboost_stacktrace_addr2line.a
52K     ./libboost_timer.a
80K     ./libboost_random.a
152K    ./libboost_container.a
152K    ./libboost_date_time.a
208K    ./libboost_prg_exec_monitor.a
232K    ./libboost_chrono.a
232K    ./libboost_fiber.a
276K    ./libboost_iostreams.a
320K    ./libboost_contract.a
404K    ./libboost_filesystem.a
776K    ./libboost_wserialization.a
828K    ./libboost_graph.a
1,2M    ./libboost_serialization.a
1,5M    ./libboost_program_options.a
2,2M    ./libboost_test_exec_monitor.a
2,2M    ./libboost_unit_test_framework.a
3,1M    ./libboost_regex.a
4,5M    ./libboost_wave.a
```
11. Найдите *топ10* самых "тяжёлых".
```sh
$ find -type f -exec du -h {} + | sort -hr | head -n 10
4,5M    ./libboost_wave.a
3,1M    ./libboost_regex.a
2,2M    ./libboost_unit_test_framework.a
2,2M    ./libboost_test_exec_monitor.a
1,5M    ./libboost_program_options.a
1,2M    ./libboost_serialization.a
828K    ./libboost_graph.a
776K    ./libboost_wserialization.a
404K    ./libboost_filesystem.a
320K    ./libboost_contract.a
```
