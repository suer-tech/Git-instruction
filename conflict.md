## Разрешение конфликтов. 
В заключение рассмотрим еще один частый сценарий,                
распространенный при одновременной работе нескольких чел                 овек. Давайте в
нашем первом локальном репозитории внесем еще какие­нибуд                     ь изменения в файл
**first.txt**, закоммитим и отправим их в главный репозиторий. А затем во в                         тором
локальном репозитории создадим файл                   **second.txt** и тоже закоммитим. Однако
если теперь из второго репозитория мы попробуем сделать                `git pus`h, то получим      
ошибку из­за конфликта изменений. Почему? Для простоты мож                       но считать, что при
отправке изменений в локальном репозитории должна быть вер                     сия, основанная на
версии главного репозитория. Тогда как мы во втором репозит                         ории пока ничего не
знаем про последний коммит                     **first.txt**. Что делать? Сначала нам нужно
получить изменения из главного репозитория, затем объедин                     ить их с нашими
изменениями, и то, что получилось, отправить на главный реп                     озиторий. Звучит
непросто, но на самом деле первые два шага сама умеет делать к                         оманда `git
pull`. Она достаточно умна, чтобы понять, что в нашем случае надо о                         бновить
файл                     **first.txt** и добавитьsecond.txt. После чего нам остается просто
отправить изменения командой `git push`. 
Итого получаем, что при отправке изменений безопасно польз                   оваться двумя
последовательными командами: 
`git pull` (проверить на наличие новых изменений в репозитории и, если                  
они есть, выкачать их и объединить с локальными изменениями)
    `git push`  (отправить изменения в репозиторий)
Таким образом, git умеет разрешать конфликты самостоятель                     но. Но к сожалению
не все. Если бы мы вместо создания                         **second.txt** во втором репозитории тоже
изменили                        ** first.txt**, то мы бы имели две измененные версии одного файла и
здесь уже git самостоятельно разрешить конфликт не может: н                     ужно вмешательство
человека. При грамотно спланированной работе команды, так                 ие ситуации
встречаются редко, и мы их рассматривать не будем. Интересу                     ющиеся могут
посмотреть в интернете или в справке git по команде                         merge в разделе *"How to   
resolve conflicts"*.