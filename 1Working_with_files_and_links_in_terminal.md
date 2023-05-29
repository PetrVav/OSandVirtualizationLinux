Операционные системы и виртуализация (Linux) (семинары)
Урок 2. Работа с файлами и ссылками
Задание:
Используя команду cat, создать два файла с данными, а затем объединить их. Просмотреть содержимое созданного файла. Переименовать файл, дав ему новое имя.
Создать несколько файлов. Создать директорию, переместить файл туда. Удалить все созданные в этом и предыдущем задании директории и файлы.
Создать файл file1 и наполнить его произвольным содержимым. Скопировать его в file2. Создать символическую ссылку file3 на file1. Создать жесткую ссылку file4 на file1. Посмотреть, какие айноды у файлов. Удалить file1. Что стало с остальными созданными файлами? Попробовать вывести их на экран.
Дать созданным файлам другие, произвольные имена. Создать новую символическую ссылку. Переместить ссылки в другую директорию.

Результат:
Текст команд, которые применялись при выполнении задания. Присылаем в формате текстового документа: задание и команды для решения (без вывода). Формат - PDF (один файл на все задания).

Сдайте задание до: 15 февр., 20:00 +03:00 UTC

petrv@petrv-linux:~$ cat > file1                  //Создал файл file1 с данными
Заполняем файл1 олололололол
араривииуиик ььтмлтлтлтл ттт
лолтслолы ршршралтлслсттсттт
оттттт Заполнили файл1ттвооаоаа

petrv@petrv-linux:~$ cat file1                    //Проверил файл file1
Заполняем файл1 олололололол
араривииуиик ььтмлтлтлтл ттт
лолтслолы ршршралтлслсттсттт
оттттт Заполнили файл1ттвооаоаа

petrv@petrv-linux:~$ cat > file2                  //Создал файл file2 с данными
ЗАполняем данными файл2 рлоллл
лттцьлцль ллчоуоцт ттттт тттт
оцттцтччиичрыррцооцттвоо ооооооо
Заполнили данными файл2

petrv@petrv-linux:~$ cat file2                    //Проверил файл file2
ЗАполняем данными файл2 рлоллл
лттцьлцль ллчоуоцт ттттт тттт
оцттцтччиичрыррцооцттвоо ооооооо
Заполнили данными файл2

petrv@petrv-linux:~$ ll                           //Проверил создались ли файлы file1 and file 2
итого 144
-rw-rw-r--  1 petrv petrv    225 фев 12 16:34  file1
-rw-rw-r--  1 petrv petrv    221 фев 12 16:35  file2

petrv@petrv-linux:~$ cat file1 file2 > file_all   //Объединил file1 и file2 в file_all
petrv@petrv-linux:~$ ll                           //Посмотрел, что создался file_all с длиной 225 + 221 = 446
итого 148
-rw-rw-r--  1 petrv petrv    225 фев 12 16:34  file1
-rw-rw-r--  1 petrv petrv    221 фев 12 16:35  file2
-rw-rw-r--  1 petrv petrv    446 фев 12 16:37  file_all

petrv@petrv-linux:~$ cat file_all                 //Посмотрел содержимое файла file_all
Заполняем файл1 олололололол
араривииуиик ььтмлтлтлтл ттт
лолтслолы ршршралтлслсттсттт
оттттт Заполнили файл1ттвооаоаа
ЗАполняем данными файл2 рлоллл
лттцьлцль ллчоуоцт ттттт тттт
оцттцтччиичрыррцооцттвоо ооооооо
Заполнили данными файл2
petrv@petrv-linux:~$

petrv@petrv-linux:~$ mv file_all newfile_all      //Переименовал файл file_all  в  newfile_all
petrv@petrv-linux:~$ ll
итого 148
-rw-rw-r--  1 petrv petrv    225 фев 12 16:34  file1
-rw-rw-r--  1 petrv petrv    221 фев 12 16:35  file2
-rw-rw-r--  1 petrv petrv    446 фев 12 16:37  newfile_all

petrv@petrv-linux:~$ touch f1 f2 f3 f4            //Создал 4 пустых файла: f1, f2, f3 and f4
petrv@petrv-linux:~$ ll
итого 148
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f1
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f2
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f3
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f4

petrv@petrv-linux:~$ mkdir test                   //Создал директорию test
petrv@petrv-linux:~$ ls -al
итого 152
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f1
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f2
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f3
-rw-rw-r--  1 petrv petrv      0 фев 12 16:38  f4
-rw-rw-r--  1 petrv petrv    225 фев 12 16:34  file1
-rw-rw-r--  1 petrv petrv    221 фев 12 16:35  file2
drwxrwxr-x  2 petrv petrv   4096 фев 12 16:39  test

petrv@petrv-linux:~$ mv f1 f2 f3 f4 test          //Переместил файлы f1 f2 f3 f4 в каталог test
petrv@petrv-linux:~$ ll

petrv@petrv-linux:~$ cd test                      //Перехожу в каталог test
petrv@petrv-linux:~/test$
petrv@petrv-linux:~/test$ ll
итого 8
drwxrwxr-x  2 petrv petrv 4096 фев 12 16:40 ./
drwxr-x--- 18 petrv petrv 4096 фев 12 16:40 ../
-rw-rw-r--  1 petrv petrv    0 фев 12 16:38 f1
-rw-rw-r--  1 petrv petrv    0 фев 12 16:38 f2
-rw-rw-r--  1 petrv petrv    0 фев 12 16:38 f3
-rw-rw-r--  1 petrv petrv    0 фев 12 16:38 f4
petrv@petrv-linux:~/test$-

petrv@petrv-linux:~/test$ cd                       //Ушел вверх
petrv@petrv-linux:~$

petrv@petrv-linux:~$ rm -rf test                   //Удалил каталог test жестко, вместе с содержимым
petrv@petrv-linux:~$ ll

petrv@petrv-linux:~$ rm file1 file2 newfile_all    //Удалил файлы file1 file2 newfile_all
petrv@petrv-linux:~$ ll

petrv@petrv-linux:~$ cat > file1                   //Создал файл file1 и заполнил его содержимым(вышел Ctrl + d)
Заполнил файл file1 содержимым
щатиоал ллбмььаььа лььмтаттатт
тотмьаоаллввььалллаллаллаллала
Заполнил файл file1 содержимым
petrv@petrv-linux:~$

petrv@petrv-linux:~$ cp file1 file2             //Скопировал файл file1 в файл file2
petrv@petrv-linux:~$ ll                         //Посмотрел - file1 and file2 с одинаковой длиной
итого 144
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file1
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file2
petrv@petrv-linux:~$ ln -s file1 file3_lns      //Создал символическую ссылку file3_lns на файл file1
petrv@petrv-linux:~$ ll
итого 144
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file1
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file2
lrwxrwxrwx  1 petrv petrv      5 фев 12 16:46  file3_lns -> file1

petrv@petrv-linux:~$ ln file1 file4_ln          //Сделал жесткую ссылку file4_ln на файл file1
petrv@petrv-linux:~$ ll
итого 148
-rw-rw-r--  2 petrv petrv    226 фев 12 16:45  file1
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file2
lrwxrwxrwx  1 petrv petrv      5 фев 12 16:46  file3_lns -> file1
-rw-rw-r--  2 petrv petrv    226 фев 12 16:45  file4_ln

petrv@petrv-linux:~$ ls -ali                    //Посмотрел какие айноды у файлов file1 и file4_ln(i - это айноды)
итого 148
1315819 -rw-rw-r--  2 petrv petrv    226 фев 12 16:45  file1      //есть айнод(1315786) и к нему прикреплены
1315819 -rw-rw-r--  2 petrv petrv    226 фев 12 16:45  file4_ln   //2 имени файла в этой директории
                                                                  //Время модификации у этих файлов одинаковое
                                                                  //т.е. это не самостоятельные файлы
-rw-rw-r--  2 petrv petrv    226 фев 12 16:45  file1        //Вот это все
-rw-rw-r--  2 petrv petrv    226 фев 12 16:45  file4_ln     //находится в айноде 1315786

petrv@petrv-linux:~$ rm file1                   //Удалил файл file1
petrv@petrv-linux:~$ ll
итого 144  
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file2
lrwxrwxrwx  1 petrv petrv      5 фев 12 16:46  file3_lns -> file1 -   //(file3_lns -> file1 -красный) -Ссылка file3_lns сломалась )
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  file4_ln

petrv@petrv-linux:~$ cat file1                 //Вывел на экран file1
cat: file1: Нет такого файла или каталога

petrv@petrv-linux:~$ cat file2                 //Вывел на экран file2
Заполнил файл file1 содержимым
щатиоал ллбмььаььа лььмтаттатт
тотмьаоаллввььалллаллаллаллала
Заполнил файл file1 содержимым

petrv@petrv-linux:~$ cat file3_lns             //Вывел на экран ссылку file3_lns
cat: file3_lns: Нет такого файла или каталога

petrv@petrv-linux:~$ cat file4_ln                  //Вывел на экран file4_ln
Заполнил файл file1 содержимым
щатиоал ллбмььаььа лььмтаттатт
тотмьаоаллввььалллаллаллаллала
Заполнил файл file1 содержимым
petrv@petrv-linux:~$

petrv@petrv-linux:~$ mv file1 newfile1         //Попытался переименовать file1 в newfile1
mv: не удалось выполнить stat для 'file1': Нет такого файла или каталога

petrv@petrv-linux:~$ mv file2 newfile2         //Переименовал file2 в newfile2

petrv@petrv-linux:~$ mv file3_lns newfile3_lns    //Переименовал символическую ссылку file3_lns в newfile3_lns

petrv@petrv-linux:~$ mv file4_ln newfile4_ln      //Переименовал жесткую ссылку file4_ln в newfile4_ln
petrv@petrv-linux:~$

petrv@petrv-linux:~$ cat newfile2
Заполнил файл file1 содержимым
щатиоал ллбмььаььа лььмтаттатт
тотмьаоаллввььалллаллаллаллала
Заполнил файл file1 содержимым

petrv@petrv-linux:~$ cat newfile3_lns
cat: newfile3: Нет такого файла или каталога

petrv@petrv-linux:~$ cat newfile4_ln
Заполнил файл file1 содержимым
щатиоал ллбмььаььа лььмтаттатт
тотмьаоаллввььалллаллаллаллала
Заполнил файл file1 содержимым

petrv@petrv-linux:~$ ll
итого 144
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile2
lrwxrwxrwx  1 petrv petrv      5 фев 12 16:46  newfile3_lns -> file1   //(Красная) Сломаная ссылка newfile3_lns(файл file1 Я удалил)
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile4_ln

petrv@petrv-linux:~$ pwd                                             //Посмотрел где нахожусь
/home/petrv

petrv@petrv-linux:~$ ln -s /home/petrv/newfile4_ln newfile4_lns_abs     //Создал символическую ссылку с абсолютным путем
petrv@petrv-linux:~$ ll
итого 148
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile2
lrwxrwxrwx  1 petrv petrv      5 фев 12 16:46  newfile3_lns -> file1   //(Красная) Сломаная ссылка newfile3_lns(файл file1 Я удалил)
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile4_ln
lrwxrwxrwx  1 petrv petrv     23 фев 12 16:55  newfile4_lns_abs -> /home/petrv/newfile4_ln

petrv@petrv-linux:~$ mkdir test                           //Создал директорию test
petrv@petrv-linux:~$ ll                                   //Посмотрел
итого 148
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile2
lrwxrwxrwx  1 petrv petrv      5 фев 12 16:46  newfile3_lns -> file1
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile4_ln
lrwxrwxrwx  1 petrv petrv     23 фев 12 16:55  newfile4_lns_abs -> /home/petrv/newfile4_ln
drwxrwxr-x  2 petrv petrv   4096 фев 12 16:56  test/                      //Директория test появилась

petrv@petrv-linux:~$ cd test                                              //Перешел в директорию test

petrv@petrv-linux:~/test$ touch file1                                     //Создал пустой файл file1
petrv@petrv-linux:~/test$ ll
итого 8
drwxrwxr-x  2 petrv petrv 4096 фев 12 16:56 ./
drwxr-x--- 18 petrv petrv 4096 фев 12 16:56 ../
-rw-rw-r--  1 petrv petrv    0 фев 12 16:56 file1

petrv@petrv-linux:~/test$ cd                                              //Вышел из каталога test

petrv@petrv-linux:~$ mv newfile3_lns newfile4_lns_abs test      //Перенес ссылки newfile3_lns и newfile4_lns_abs в каталог test

petrv@petrv-linux:~$ ll test                                              //Посмотрел в каталоге test:  
итого 8                                                                   //- Ссылки newfile3 и newfile4_lns_abs работают
drwxrwxr-x  2 petrv petrv 4096 фев 12 16:58 ./
drwxr-x--- 18 petrv petrv 4096 фев 12 16:58 ../
-rw-rw-r--  1 petrv petrv    0 фев 12 16:56 file1
lrwxrwxrwx  1 petrv petrv    5 фев 12 16:46 newfile3_lns -> file1   //Ссылка newfile3_lns заработала потому что в test/ был file1
lrwxrwxrwx  1 petrv petrv   23 фев 12 16:55 newfile4_lns_abs -> /home/petrv/newfile4_ln
petrv@petrv-linux:~$

petrv@petrv-linux:~$ ll
итого 148
drwxr-x--- 18 petrv petrv   4096 фев 12 16:58  ./
drwxr-xr-x  3 root  root    4096 фев  3 04:05  ../
-rw-------  1 petrv petrv   2633 фев 11 23:21  .bash_history
-rw-r--r--  1 petrv petrv    220 фев  3 04:05  .bash_logout
-rw-r--r--  1 petrv petrv   3771 фев  3 04:05  .bashrc
drwx------ 15 petrv petrv   4096 фев 10 13:18  .cache/
drwx------ 17 petrv petrv   4096 фев 10 16:46  .config/
-rw-------  1 petrv petrv     38 фев 10 02:25  .lesshst
drwxrwxr-x  4 petrv petrv   4096 фев 11 00:23  lesson2/
drwx------  3 petrv petrv   4096 фев  3 05:06  .local/
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile2
-rw-rw-r--  1 petrv petrv    226 фев 12 16:45  newfile4_ln
-rw-r--r--  1 petrv petrv    360 фев  9 18:03  .pam_environment
-rw-r--r--  1 petrv petrv    807 фев  3 04:05  .profile
drwxrwx---  1 root  vboxsf 20480 фев 11 23:35  shared/
drwx------  5 petrv petrv   4096 фев  5 11:38  snap/
drwx------  2 petrv petrv   4096 фев  5 12:43  .ssh/
-rw-r--r--  1 petrv petrv      0 фев  3 19:15  .sudo_as_admin_successful
drwxrwxr-x  2 petrv petrv   4096 фев 12 16:58  test/
-rw-r-----  1 petrv petrv      5 фев 12 13:02  .vboxclient-clipboard.pid
-rw-r-----  1 petrv petrv      5 фев 12 13:02  .vboxclient-draganddrop.pid
-rw-r-----  1 petrv petrv      5 фев 12 13:02  .vboxclient-seamless.pid
-rw-r-----  1 petrv petrv      5 фев 12 13:02  .vboxclient-vmsvga-session-tty2.pid
-rw-------  1 petrv petrv   9905 фев 10 15:17  .viminfo
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06  Видео/
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06  Документы/
drwxr-xr-x  3 petrv petrv   4096 фев 10 00:26  Загрузки/
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06  Изображения/
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06  Музыка/
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06  Общедоступные/
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06 'Рабочий стол'/
drwxr-xr-x  2 petrv petrv   4096 фев  9 18:06  Шаблоны/
petrv@petrv-linux:~$
